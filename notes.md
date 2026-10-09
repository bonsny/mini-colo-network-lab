# Notes
- Step 1: set up OrbStack Ubuntu 24.04, Docker, Containerlab 0.79, gh CLI. Learned: groups need re-login to apply.
- Step 2: host1 ARP cache empty -> after ping shows r1 MAC aa:c1:ab:85:5a:f3 (matches r1 eth1). First ping 1.73ms vs ~0.11ms after = ARP resolution cost. Ping to host2 fails: r1 has no route to 10.2.2.0/24 -> needs OSPF.
- Step 3: OSPF Full/- with 2.2.2.2 (dash = no DR on point-to-point). r1 learned 10.2.2.0/24 via proto ospf. host1->host2 ping works, ttl=62 (64 minus 2 routers).
- Step 3 wrap-up: LSDB has 2 router LSAs (1.1.1.1, 2.2.2.2), same Seq#/CkSum on r1 and r2 = identical map. r1 learned 10.2.2.0/24 from r2's LSA (stub network). Route [110/20]: AD 110, cost 20. P2P link, hello 10 / dead 40.
