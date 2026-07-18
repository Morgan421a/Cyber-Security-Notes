---
aliases:
  - LB
---
- Load Balancer
- Helps web servers handle traffic by first checking the requests and using algorithms (e.g round-robin, weighted, etc) to see which server is currently best suited to deal with each one.
- Carries out health checks to ensure servers are running properly, if response = inappropriate or absent, stops sending requests to it until it responds as it should again.