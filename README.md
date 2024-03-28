This is a repository to reproduce garden.io issue: https://github.com/garden-io/garden/issues/5891

To reproduce do these steps:
```
> export CONTEXT_NAME=k8s_ctx
> export NAMESPACE=k8s_namespace
> garden up -l 4

```


So here is an execution log on my env:
```
garden up -l 4

┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈ Running deploy --logs -l 4 command... ┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈
ℹ garden-dashboard          → [debug] Initializing Garden Cloud API client.
[debug] No auth token found, proceeding without access to the Garden dashboard. Command results for this command run will not be available in the Garden dashboard.
[verbose] Initializing Garden context for dev (none found for key)
[debug] Instance key: env=dev
ℹ garden-dashboard          → You are not logged in. To use the Garden dashboard, log in with the garden login command.
ℹ garden-dashboard          → Learn more at: https://docs.garden.io/using-garden/dashboard
[debug] Garden context updated for key env=dev
ℹ git                       → [debug] Scanning project root at /home/yauhen/ws/helm/hello-world
  → Includes: (none)
  → Excludes: (none)
ℹ git                       → [debug] Found 5 files in project root /home/yauhen/ws/helm/hello-world
[debug] Found 5 files in path /home/yauhen/ws/helm/hello-world, filtering by 1 include and 6 exclude globs
[debug] Include globs: **/*garden.y*ml
[debug] Exclude globs: .garden/**/*, .git/**/*, .gitmodules, .garden/**/*, debug-info*/**, **/.garden/**/*
[debug] Found 1 files in path /home/yauhen/ws/helm/hello-world after glob matching
[debug] Scanned and found 1 actions, 0 workflows and 0 modules
[debug] Watcher: Add 1 paths
ℹ providers                 → Resolving providers...
ℹ exec                      → Configuring provider...
ℹ templated                 → [debug] Configuring provider...
ℹ container                 → [debug] Configuring provider...
✔ exec                      → Provider configured
✔ templated                 → [debug] Provider configured
✔ container                 → [debug] Provider configured
✔ container                 → [debug] Provider status cached
ℹ providers                 → [verbose] resolve provider container is ready.
ℹ kubernetes                → Configuring provider...
✔ kubernetes                → Provider configured
✔ exec                      → Provider status cached
ℹ providers                 → [verbose] resolve provider exec is ready.
✔ templated                 → [debug] Provider status cached
ℹ providers                 → [verbose] resolve provider templated is ready.
✔ kubernetes                → Provider status cached
ℹ providers                 → [verbose] resolve provider kubernetes is ready.
✔ providers                 → Finished resolving providers (took 0.3 sec)
ℹ providers                 → All provider statuses were cached. Run with --force-refresh to force a refresh of provider statuses.
ℹ graph                     → Resolving actions and modules...
ℹ git                       → [debug] Scanning Deploy action hello-world root at /home/yauhen/ws/helm/hello-world
  → Includes: (none)
  → Excludes: (none)
ℹ git                       → [debug] Found 5 files in Deploy action hello-world root /home/yauhen/ws/helm/hello-world
ℹ graph                     → [debug] Found 5 files in path /home/yauhen/ws/helm/hello-world, filtering by 1 include and 5 exclude globs
ℹ graph                     → [debug] Include globs: **/*
ℹ graph                     → [debug] Exclude globs: .git/**/*, .gitmodules, .garden/**/*, debug-info*/**, **/.garden/**/*
ℹ graph                     → [debug] Found 5 files in path /home/yauhen/ws/helm/hello-world after glob matching
✔ graph                     → Finished resolving graph (took 0 sec)
ℹ deploy.hello-world        → [debug] resolve Deploy type=helm name=hello-world is ready.
ℹ [monitors]                → [debug] Subscribing command deploy to monitor log monitor for Deploy type=helm name=hello-world.
ℹ [monitors]                → [debug] Adding monitor log monitor for Deploy type=helm name=hello-world.
ℹ [monitors]                → [debug] log monitor for Deploy type=helm name=hello-world is starting.
ℹ [monitors]                → Starting log monitor for Deploy type=helm name=hello-world...
ℹ deploy.hello-world        → [debug] resolve Deploy type=helm name=hello-world is ready.
ℹ deploy.hello-world        → Getting status for Deploy hello-world (type helm)...
ℹ deploy.hello-world        → Status is missing, hello-world will be deployed
ℹ deploy.hello-world        → Deploying hello-world (type helm) at version v-ed19d817c0...
ℹ deploy.hello-world        → [debug] Failed getting deployed resources. Retrying...
ℹ deploy.hello-world        → [verbose] [helm] NAME: hello-world
ℹ deploy.hello-world        → [verbose] [helm] LAST DEPLOYED: Thu Mar 28 16:41:49 2024
ℹ deploy.hello-world        → [verbose] [helm] NAMESPACE: yauhenl
ℹ deploy.hello-world        → [verbose] [helm] STATUS: deployed
ℹ deploy.hello-world        → [verbose] [helm] REVISION: 1
ℹ deploy.hello-world        → [verbose] [helm] TEST SUITE: None
ℹ deploy.hello-world        → [debug] Kubernetes: Getting API resource info for group batch/v1
[debug] <No running containers found for Job hello-world. Will retry in 10s...>
ℹ deploy.hello-world        → [kubernetes] Waiting for resources to be ready...
ℹ deploy.hello-world        → [verbose] [kubernetes] Waiting for resources to be ready...
ℹ deploy.hello-world        → [verbose] [kubernetes] No resources to wait for
ℹ deploy.hello-world        → [kubernetes] No resources to wait for
✔ deploy.hello-world        → Done (took 3.2 sec)
ℹ deploy.hello-world        → [verbose] Deploy type=helm name=hello-world is ready.
ℹ [monitors]                → [debug] Subscribing command deploy to monitor port proxy for Deploy type=helm name=hello-world.
ℹ [monitors]                → [debug] Adding monitor port proxy for Deploy type=helm name=hello-world.
ℹ [monitors]                → [debug] port proxy for Deploy type=helm name=hello-world is starting.
ℹ [monitors]                → Starting port proxy for Deploy type=helm name=hello-world...
ℹ [monitors]                → [debug] port proxy for Deploy type=helm name=hello-world is started.
[debug] Done flushing all events and log entries.

┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈ Command deploy completed successfully! ┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈
[debug] <No running containers found for Job hello-world. Will retry in 10s...>

[debug] <No running containers found for Job hello-world. Will retry in 10s...>
```

Garden supposed to show logs of my Deploy action, however there is none.


In the meantime here is an output of a job pod:
```
> kubectl logs -f hello-world-lnwj6

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (arm64v8)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
```
