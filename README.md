# Windows RDP VPS: What a Usable Plan Costs, Which Evoxt Tier Fits Your Workload, and the Windows Licensing Fine Print (Full Plan Table)

A usable Windows RDP VPS from Evoxt costs $11.99 per month. That's VM-2: 2 vCores, 4 GB RAM, 30 GB of storage, and the first tier in the lineup that behaves like a normal desktop instead of a demo. One step down, VM-1 at $5.99 runs Windows on a single core with 2 GB RAM and 20 GB of disk, which is fine when the machine has exactly one job. One step up, VM-4 at $23.99 doubles RAM to 8 GB and disk to 60 GB, and that's where most people running a trading terminal, a browser and a few background scripts end up.

The rest of this page is about choosing between those three tiers, and about the two things that decide whether a cheap Windows box stays usable after week one: how much disk Windows and its updates consume, and who is responsible for the Windows licence.

> **Most readers should start at VM-4 ($23.99/month).** 4 vCores, 8 GB RAM and 60 GB of storage covers Windows plus a real application stack, and it leaves room for a second person logging in. Choose VM-2 ($11.99) if the budget is fixed and you can manage 30 GB of disk. Choose VM-1 ($5.99) only for a single app, single user, no browser habit.
>
> 👉 [Check Evoxt's current plan prices and pick your tier](https://bit.ly/EvoXt)

## Evoxt Windows VPS plans and prices

| Plan | vCPU / RAM | Storage | Price (USD/month) | Order |
| --- | --- | --- | --- | --- |
| VM-0.5 | 1 vCore / 512 MB | 5 GB | $2.99 | [Order VM-0.5](https://bit.ly/EvoXt) |
| VM-0.75 | 1 vCore / 1 GB | 10 GB | $4.99 | [Order VM-0.75](https://bit.ly/EvoXt) |
| VM-1 | 1 vCore / 2 GB | 20 GB | $5.99 | [Order VM-1](https://bit.ly/EvoXt) |
| VM-1.5 | 2 vCores / 2 GB | 20 GB | $6.95 | [Order VM-1.5](https://bit.ly/EvoXt) |
| VM-2 | 2 vCores / 4 GB | 30 GB | $11.99 | [Order VM-2](https://bit.ly/EvoXt) |
| VM-3 | 4 vCores / 4 GB | 30 GB | $14.99 | [Order VM-3](https://bit.ly/EvoXt) |
| VM-4 | 4 vCores / 8 GB | 60 GB | $23.99 | [Order VM-4](https://bit.ly/EvoXt) |
| VM-6 | 8 vCores / 8 GB | 60 GB | $29.99 | [Order VM-6](https://bit.ly/EvoXt) |
| VM-8 | 8 vCores / 16 GB | 80 GB | $47.99 | [Order VM-8](https://bit.ly/EvoXt) |
| VM-16 | 16 vCores / 32 GB | 100 GB | $95.99 | [Order VM-16](https://bit.ly/EvoXt) |

Prices are USD, billed monthly. Monthly transfer scales with the tier on Evoxt's Premium network, from 250 GB on VM-0.5 up to 5 TB on VM-16. Evoxt revises its lineup from time to time, so confirm the specification and the price on the order screen before you pay.

## How much RAM and disk does a Windows desktop actually need?

2 vCPU and 4 GB is the floor for Windows, and 4 vCPU with 8 GB is what normal remote-desktop use wants. EDIS Global publishes that distinction more plainly than most hosts: it calls 2 vCPU / 4 GB "a starting point for a basic Windows setup, not a recommendation for every workload", and points anyone running regular RDP sessions or several services at 4 vCPU and 8 GB or more. EDIS also flags a mistake that spec tables encourage, namely treating RAM and cores as interchangeable. An 8 GB plan with 2 cores still doesn't meet a 4-core recommendation. RAM sets how much can be open at once; cores set how fast the machine works through parallel load.

Disk is the number Evoxt buyers underestimate. Windows Server plus its update cache takes a real bite out of the volume before you install anything, and the competing Windows plans are sized accordingly: EDIS's cheapest Windows configuration ships 45 GB of SSD, Infrawire's Hong Kong entry ships 40 GB of NVMe. Evoxt's VM-2 gives 30 GB and VM-1 gives 20 GB, which is the tightest storage in this comparison at the entry level.

What that means in practice:

- **20 GB (VM-1)** fits Windows, one terminal or one app, and very little else. You will be clearing update caches and watching free space.
- **30 GB (VM-2, VM-3)** fits Windows, a browser and a trading terminal with logs trimmed. Workable, not generous.
- **60 GB (VM-4, VM-6)** is the first tier where you stop thinking about disk. Trade history, browser profiles and app updates all fit.

## Where the Evoxt plan ladder gets interesting

Evoxt's ladder isn't a straight line, and two of the rungs are better value than their neighbours depending on what your workload is short of.

VM-3 at $14.99 gives you 4 cores and 4 GB for $3 more than VM-2's 2 cores and 4 GB, with the same 30 GB disk. If your work is parallel batch processing, that's a cheap way to double core count. It does nothing for a desktop that's short of memory, so don't read it as an upgrade for general use. VM-6 is the mirror image: $29.99 buys 8 cores and 8 GB against VM-4's 4 cores and 8 GB, $6 more for four extra cores and identical RAM and disk.

The benchmark record backs up something Evoxt claims in its own plan description, that its VMs run at 3.5 GHz+ CPU frequency and lean on single-core speed rather than core count. VPSBenchmarks has scored four of these tiers, and the price-weighted results favour the cheap single-core plan: VM-1 scores 80 on price-weighted value against 72 for VM-2, 69 for VM-4 and 55 for VM-8. Raw performance does climb with price (VM-1 scored 53, VM-4 scored 60, VM-8 scored 62 in the same test series), but not by much, because most of what you're buying further up the ladder is RAM and disk rather than clock speed.

For a MetaTrader EA, a scraping script or any single-threaded Windows tool, that changes the buying logic. Moving from VM-1 to VM-4 costs four times as much and buys roughly 13% more raw benchmark score. You move up because you need RAM, disk or a second session, not because the cheaper box is slow.

Skip VM-0.5 and VM-0.75 for Windows. 512 MB and 1 GB exist because Evoxt also sells Linux VMs, and a Windows desktop on 1 GB will spend its life swapping. The same caution applies outside Evoxt: HOSTKEY advertises a €1.27/month tier with 1 vCPU and 0.5 GB RAM, which is not a Windows desktop no matter how the page frames it.

## Windows image and licence: the part Evoxt doesn't spell out

Evoxt lists Windows among its deployable operating systems alongside Ubuntu, Debian and CentOS, but its public pages don't state which Windows Server edition you receive, whether a licence is bundled, or whether the image is an evaluation build. Confirm that with support before you pay, because the answer changes the real cost of the machine.

The industry default among budget Windows hosts is an evaluation image with the licence left to you. EDIS Global says so explicitly: it offers Windows Server 2025, 2022 and 2019 evaluation images plus Windows 10 and 11 images in its dashboard, and puts Windows, application, licence, security and backup management on the customer. Infrawire offers a wider spread of Windows versions, up to Server 2025 and Windows 11, without stating its licensing model either. If your plan is a few weeks of testing, an evaluation image is fine. If the box is going into production, price a proper licence into year one.

Two more things worth knowing before you install anything:

**A reinstall wipes the disk.** EDIS states it outright for its own platform, and it's true of any OS reinstall on a VPS. Evoxt includes a weekly offsite backup with every VM at no extra cost and lets you restore from the panel, which covers accidents but not the last six days of work. Keep your own copy of anything you can't rebuild.

**Multiple simultaneous users need checking.** Sharing one desktop between a couple of people is the most common reason to buy a bigger plan, but concurrent RDP sessions on Windows normally require extra licensing from Microsoft. Ask what the image you're given supports if more than one person will log in.

👉 [Open the Evoxt console to confirm the Windows template before you pay](https://bit.ly/EvoXt)

## What the monthly price includes, and what year two costs

Every Evoxt VM ships with a weekly offsite backup, a control-panel firewall where you pick open and closed ports per machine, IPv6, usage charts for CPU, RAM, bandwidth and storage, a browser-based VNC console, an admin REST API, VM cloning, and upgrades you trigger from the console in a few clicks without a reinstall. IP addresses can be swapped and reassigned between servers, and additional floating IPs are available for failover setups.

What isn't there matters just as much. There's no hourly billing, so you can't spin a box up for three days and drop it. Reverse DNS isn't offered, which rules Evoxt out if you intend to run a mail server. No plan in the published lineup includes GPU acceleration.

On total cost, Evoxt publishes a single monthly price per plan with no separate renewal rate, so budget the same figure in year two as in year one:

| Plan | Monthly | Year one | Year two |
| --- | --- | --- | --- |
| VM-1 | $5.99 | $71.88 | $71.88 |
| VM-2 | $11.99 | $143.88 | $143.88 |
| VM-4 | $23.99 | $287.88 | $287.88 |
| VM-8 | $47.99 | $575.88 | $575.88 |

If a discounted figure shows up at checkout, check what it renews at before you commit. A host that advertises a steep first-year price and renews at three times that is not cheaper than this over two years, whatever the headline says.

I couldn't find a published money-back window on Evoxt's pages. If a refund option is part of your decision, get the terms from support in writing before paying, especially on a first Windows deployment where you're still testing whether the image and the disk size suit you.

## Limits that decide whether Evoxt is the right host here

**DDoS protection is disputed.** Evoxt's own product page says every server is equipped with DDoS protection. VPSBenchmarks' feature table for the host marks DDoS protection as not included. If filtering is a hard requirement, get a written answer rather than trusting either page.

**Outbound mail policy is unpublished.** Several Windows VPS hosts block port 25 by default to limit spam; Infrawire blocks it on every plan. Evoxt's public pages don't state a port policy, so ask if your app sends mail.

**It's unmanaged.** You get Administrator access over RDP and an OS template. Windows updates, application installs, hardening and backups of your own data are yours to handle.

**No hourly billing, no reverse DNS, no GPU.**

**It isn't for Linux workloads.** If what you actually need is a box for a website, a container or a bot that runs happily on Debian, a Windows RDP VPS is the wrong purchase twice over: you pay for a Windows-sized disk and RAM footprint you won't use.

## How Evoxt compares with other Windows RDP VPS options

Four hosts with verified Windows VPS listings, all priced in different currencies and aimed at different regions. Don't rank them on the headline number.

| Host | Windows entry configuration | Listed price | What's different |
| --- | --- | --- | --- |
| Evoxt | 2 vCores / 4 GB / 30 GB | $11.99/mo | 3.5 GHz+ single-core clocks, weekly offsite backups, monthly billing only |
| LightNode | 1 vCPU / 2 GB / 50 GB NVMe | from $7.71/mo | Hourly billing, deployment in 1–2 minutes, 40+ locations |
| Infrawire (Hong Kong) | 2 cores / 4 GB / 40 GB NVMe | €8.30/mo | Unlimited traffic on a 1 Gbps port, 7-day money-back, port 25 blocked |
| EDIS Global | 2 vCPU / 4 GB / 45 GB SSD | €14.69–€17.19/mo | Around 50 locations, ~15-minute install, evaluation Windows images |

LightNode's $7.71 entry is a 1 vCPU / 2 GB machine, so it isn't the same class as Evoxt's VM-2. Infrawire's €8.30 is priced in euros, sits in Hong Kong, and includes unlimited traffic. EDIS lands above Evoxt in price once you match the RAM and disk. Evoxt's edge in this group is clock speed per dollar and included backups; its disadvantage is the tighter disk allocation and the missing hourly option.

## Questions people ask before ordering

**What does RDP mean here?** Remote Desktop Protocol is Microsoft's remote access standard, and it's what lets you use a Windows machine somewhere else as if you were sitting in front of it. A Windows RDP VPS is a virtual server with that service switched on, reachable at your VM's IP on TCP port 3389 with full Administrator credentials.

**Can I install my own software?** Yes. You have Administrator access, so desktop applications, trading terminals, automation tools and drivers install the same way they would locally. Licensing for commercial software stays with you.

**Can I connect from a Mac, iPhone or Android?** Yes. Windows has Remote Desktop Connection built in, and Microsoft ships official Remote Desktop clients for macOS, iOS and Android. On Linux, Remmina or FreeRDP do the job.

**Can a Linux server do RDP?** Yes, with xrdp installed, or with a desktop image that supports RDP out of the box. Evoxt sells Linux templates too, though a Linux box doesn't need a Windows-sized plan.

**How long until the machine is ready?** A few minutes. Evoxt emails the VM credentials automatically, and one published setup walkthrough puts the whole deployment at around two and a half minutes from payment to login details.

**Can I change plans later?** Yes. Evoxt supports upgrades from the admin console in a few clicks, and Infrawire's comparison point is worth keeping in mind: some hosts resize without a reinstall, some don't, so confirm the behaviour before you outgrow a tier.

## Which plan to buy

Match the plan to what the machine has to hold open, not to how impressive the spec looks:

- **One app, one user, no browser:** VM-1 at $5.99. Just accept that 20 GB needs watching.
- **A normal Windows desktop (browser, terminal, two or three tools):** VM-2 at $11.99, or VM-4 at $23.99 if you want disk headroom and room for a second session.
- **Core-hungry batch jobs:** VM-3 at $14.99 or VM-6 at $29.99, where the extra cores cost $3 and $6 respectively.
- **Multi-user or heavy local data:** VM-8 at $47.99, and only once you've measured that 8 GB isn't enough.

Two things to settle before you pay: which Windows Server edition the template gives you, and whether that image carries a licence you'd have to buy separately. Both answers change the two-year cost more than the difference between any two plans on the table. If you're still unsure, the cheapest way to find out is a one-month VM-2 and an honest look at Task Manager after a week of real use.

👉 [Open the Evoxt console and deploy the Windows plan you picked](https://bit.ly/EvoXt)
