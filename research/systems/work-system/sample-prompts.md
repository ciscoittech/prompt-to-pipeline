# Work System — Prompt Comparison

## The Basic Prompt (What Most People Do)

```
Help me troubleshoot a network connectivity issue.
The server can't reach the database.
```

**What you get**: Generic troubleshooting steps. "Check ping. Check firewall rules. Check DNS." No awareness of your specific environment, no structured methodology, no verification steps.

---

## The System Prompt (All Components Working)

When a user types `/troubleshoot`, the system:

1. **Loads context** (State): Reads the per-client project file — knows the topology, device inventory, addressing scheme, recent changes, known issues
2. **Loads skill** (Skill): Domain knowledge for that platform — evaluation orders, configuration syntax, common failure modes
3. **Queries RAG** (Connection): Searches 80K+ vendor doc chunks for relevant procedures
4. **Enforces methodology** (Flow): Follows the 5-step process — won't skip to "try this fix" without gathering data first

Here's what the interaction actually looks like:

```
User: /troubleshoot
      Server 10.1.50.20 can't reach database at 10.2.30.15

System [reads project context]:
  - Client: [loaded from per-context file]
  - Topology: Server is in VLAN 50 (Data), DB is in VLAN 30 (Database)
  - Inter-VLAN routing: Core switch, no firewall between these VLANs
  - Recent changes: VLAN 30 ACL updated 2 days ago (from change log)

System [GATHER phase]:
  "The server and database are in different VLANs routed through your
   core switch. I see VLAN 30 had an ACL change 2 days ago.

   First, can you run this from the server and paste the output?
   > ping 10.2.30.15
   > traceroute 10.2.30.15"

[One question at a time — doesn't ask 5 things at once]

User: [pastes output — ping fails at hop 2]

System [ISOLATE phase]:
  "Traffic dies at the core switch (hop 2). This is Layer 3,
   not application. Given the recent ACL change on VLAN 30,
   let's check that first.

   Run this on the core switch:
   > show access-lists [ACL-name]

   I'm looking for whether the new ACL permits traffic from
   10.1.50.0/24 to 10.2.30.0/24 on port 5432 (PostgreSQL)."

[Knows the port because the project file says it's a PostgreSQL DB]
[References the specific ACL from the change log]
```

---

## The Improvement at Each Stage

| Aspect | Basic Prompt | System |
|--------|-------------|--------|
| Environment awareness | None — you re-explain every time | Loaded from per-context state file |
| Methodology | Jump to guessing | Enforced: Gather → Isolate → Diagnose → Resolve → Prevent |
| Domain knowledge | Generic networking | 518-line skill with platform-specific syntax and procedures |
| Documentation access | None | 80K+ vendor doc chunks searched automatically |
| Question style | Asks 5 things at once | One question at a time, builds understanding |
| Recent changes | Not considered | Read from change log in context file |
| Output safety | Might suggest destructive commands | Advisor-only: "review before applying" on every command |
| Post-resolution | Nothing | Documents root cause + prevention (step 5) |
