# Notes
- Step 1: set up OrbStack Ubuntu 24.04, Docker, Containerlab 0.79, gh CLI. Learned: groups need re-login to apply.
- Step 2: host1 ARP cache empty -> after ping shows r1 MAC aa:c1:ab:85:5a:f3 (matches r1 eth1). First ping 1.73ms vs ~0.11ms after = ARP resolution cost. Ping to host2 fails: r1 has no route to 10.2.2.0/24 -> needs OSPF.
