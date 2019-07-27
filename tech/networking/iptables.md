# iptables

![State diagram](https://www.booleanworld.com/wp-content/uploads/2017/06/Untitled-Diagram.png)

## Quick Notes

- Create a new chain (-N).
- Delete an empty chain (-X).
- Change the policy for a built-in chain. (-P).
- List the rules in a chain (-L).
- Flush the rules out of a chain (-F).
- Zero the packet and byte counters on all rules in a chain (-Z).

- Append a new rule to a chain (-A).
- Insert a new rule at some position in a chain (-I).
- Replace a rule at some position in a chain (-R).
- Delete a rule at some position in a chain, or the first that matches (-D).

## References

- https://www.booleanworld.com/depth-guide-iptables-linux-firewall/
- https://netfilter.org/documentation/HOWTO//packet-filtering-HOWTO-7.html
- https://www.digitalocean.com/community/tutorials/iptables-essentials-common-firewall-rules-and-commands
- https://www.unix-ninja.com/p/An_iptables_cheat-sheet
- NAT: https://www.karlrupp.net/en/computer/nat_tutorial