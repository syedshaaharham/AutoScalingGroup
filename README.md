# Multi-AZ Web App — ALB + Auto Scaling Group

This project is a fully working **Multi-AZ web application** running across **2 Availability Zones** behind an **Application Load Balancer (ALB)** and **Auto Scaling Group (ASG)** — built to demonstrate high availability and self-healing infrastructure on AWS.

---

## What I Built

A web app deployed across 2 AZs with an ALB distributing traffic and an ASG managing EC2 instances. Then I terminated an instance mid-traffic to see what would actually happen.

**The app never went down.**

- ALB detected the unhealthy instance and immediately stopped routing traffic to it
- ASG automatically launched a fresh replacement
- The whole recovery happened within seconds — without me touching anything

---

## Architecture

```
Internet
    ↓
Application Load Balancer (ALB)
    ↓              ↓
  AZ-1           AZ-2
  EC2            EC2
  (Auto Scaling Group spans both)
```

---

## AWS Services Used

| Service | Purpose |
|---|---|
| EC2 | Web server instances |
| Application Load Balancer | Distributes traffic across AZs |
| Auto Scaling Group | Automatically replaces unhealthy instances |
| Launch Template | Defines instance configuration |
| Target Group | Health checks and traffic routing |
| VPC + Subnets | Network isolation across 2 AZs |

---

## Key Concepts Demonstrated

**High Availability** — Running across 2 AZs means no single point of failure. If one AZ goes down, traffic automatically shifts to the other.

**Self-Healing Infrastructure** — ASG continuously monitors instance health. The moment an instance becomes unhealthy, ASG terminates it and launches a replacement automatically.

**Elastic Scaling** — ASG scales out when demand increases and scales in when it drops — no manual intervention needed.

---

## Why This Matters at Scale

This exact same mechanism is what keeps the world running:

- When **Uber** surges on New Year's Eve and millions request rides simultaneously, ASG scales out instantly
- When **Instagram** goes viral after a major event and traffic spikes within minutes, ALB distributes every request across healthy instances without a single user seeing an error
- When **Amazon** gets hit with millions of orders on Prime Day, no engineer is manually provisioning servers — the infrastructure responds on its own

---

## What I Learned

- How ALB health checks detect and respond to unhealthy instances in real time
- How ASG activity logs show exactly what happened and when
- The difference between *using* AWS and *understanding* how it behaves under failure
- Why Multi-AZ is the baseline for any production-grade architecture

---

## Live Demo

A full video walkthrough showing the instance termination and automatic recovery in real time is included in this repo.

---

## Connect

Built by **Syed Shah Arham** as part of a hands-on AWS Cloud Engineering journey.

- LinkedIn: [linkedin.com/in/syedshaharham](https://linkedin.com/in/syedshaharham)
- GitHub: [github.com/syedshaharham-2006](https://github.com/syedshaaharham)

---

*The foundation is being built. One project at a time. 🚀*
