# 🐳 Docker & Containerization Interview Scenarios & Optimization Runbooks

> Production Docker interview questions, multi-stage build optimization, container security, cgroup resource limits, OOM triage, and rootless setups.

<!-- Total Scenarios: 262 | Author: Naveed Ahmed -->

[![Live Interactive Simulator](https://img.shields.io/badge/Live_Simulator-interview.naveedkumbhar.com-00d2ff?style=for-the-badge&logo=googlechrome&logoColor=white)](https://interview.naveedkumbhar.com/?cat=docker)
[![Total Scenarios](https://img.shields.io/badge/Scenarios-262_Live-4ade80?style=for-the-badge)](https://interview.naveedkumbhar.com/?cat=docker)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)
[![Author](https://img.shields.io/badge/Author-Naveed_Ahmed-purple?style=for-the-badge&logo=github)](https://github.com/naveedkumbhar)

---

### 🚀 Interactive Practice Mode Available

All **262 scenarios** in this repository are interactive on the live practice engine with search, category filtering, bookmarking, and timer modes:
👉 **[Launch Interactive Simulator on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)**

---

## 📑 Scenarios Directory

1. [CI/CD Pipeline Succeeds but New Version Isn't Deployed — Debugging](#scenario-1-ci-cd-pipeline-succeeds-but-new-version-isn-t-deployed-debugging)
2. [Troubleshooting ImagePullBackOff & ErrImagePull — 4 Root Causes](#scenario-2-troubleshooting-imagepullbackoff-errimagepull-4-root-causes)
3. [Azure Kubernetes Service (AKS) — Architecture, Deployment & Troubleshooting](#scenario-3-azure-kubernetes-service-aks-architecture-deployment-troubleshooting)
4. [CI/CD Q21: You need to build a Docker image in a GitLab CI pipeline but the pipeline runner uses Docker itself How do you solve the Docker-in-Docker problem [L2]](#scenario-4-ci-cd-q21-you-need-to-build-a-docker-image-in-a-gitlab-ci-pipeline-but-the-pipeline-runner-uses-docker-itself-how-do-you-solve-the-docker-in-docker-problem-l2)
5. [CI/CD Q22: Your Docker images are huge (3GB) CI pushes take forever How do you reduce image size [L2]](#scenario-5-ci-cd-q22-your-docker-images-are-huge-3gb-ci-pushes-take-forever-how-do-you-reduce-image-size-l2)
6. [CI/CD Q23: Youre building microservices and you want every services Docker image to be uniquely and traceably tagged Whats your tagging strategy [L3]](#scenario-6-ci-cd-q23-youre-building-microservices-and-you-want-every-services-docker-image-to-be-uniquely-and-traceably-tagged-whats-your-tagging-strategy-l3)
7. [Docker Q1: A container exits immediately after starting How do you debug it [L1]](#scenario-7-docker-q1-a-container-exits-immediately-after-starting-how-do-you-debug-it-l1)
8. [Docker Q2: Your Docker build fails with no space left on device on the CI server What do you do [L2]](#scenario-8-docker-q2-your-docker-build-fails-with-no-space-left-on-device-on-the-ci-server-what-do-you-do-l2)
9. [Docker Q3: A containerized app cant connect to a database container on the same Docker host Whats wrong [L2]](#scenario-9-docker-q3-a-containerized-app-cant-connect-to-a-database-container-on-the-same-docker-host-whats-wrong-l2)
10. [Docker Q4: Your Docker image is 2GB How do you reduce it [L2]](#scenario-10-docker-q4-your-docker-image-is-2gb-how-do-you-reduce-it-l2)
11. [Docker Q5: How do containers in the same pod (Kubernetes) communicate vs containers in different pods [L2]](#scenario-11-docker-q5-how-do-containers-in-the-same-pod-kubernetes-communicate-vs-containers-in-different-pods-l2)
12. [Docker Q6: You need to run a Docker container with access to GPU How [L3]](#scenario-12-docker-q6-you-need-to-run-a-docker-container-with-access-to-gpu-how-l3)
13. [Docker Q7: A container is consuming 100% CPU How do you limit it without restarting [L2]](#scenario-13-docker-q7-a-container-is-consuming-100-cpu-how-do-you-limit-it-without-restarting-l2)
14. [Docker Q8: Explain the difference between COPY and ADD in a Dockerfile [L2]](#scenario-14-docker-q8-explain-the-difference-between-copy-and-add-in-a-dockerfile-l2)
15. [Docker Q9: Your container needs to run as a non-root user for security How do you set this up [L3]](#scenario-15-docker-q9-your-container-needs-to-run-as-a-non-root-user-for-security-how-do-you-set-this-up-l3)
16. [Docker Q10: What is the difference between CMD and ENTRYPOINT [L2]](#scenario-16-docker-q10-what-is-the-difference-between-cmd-and-entrypoint-l2)
17. [Docker Q11: How do you share data between the host and a container [L2]](#scenario-17-docker-q11-how-do-you-share-data-between-the-host-and-a-container-l2)
18. [Docker Q12: You have a microservices app with 10 containers How do you manage them locally [L3]](#scenario-18-docker-q12-you-have-a-microservices-app-with-10-containers-how-do-you-manage-them-locally-l3)
19. [Docker Q13: A container is running but your app inside it crashed Docker shows the container as Up Why [L2]](#scenario-19-docker-q13-a-container-is-running-but-your-app-inside-it-crashed-docker-shows-the-container-as-up-why-l2)
20. [Docker Q14: How do you view resource usage (CPU memory) of running containers [L2]](#scenario-20-docker-q14-how-do-you-view-resource-usage-cpu-memory-of-running-containers-l2)
21. [Docker Q15: Your Docker Compose app needs to wait for a database to be ready before starting the app container How do you implement this [L3]](#scenario-21-docker-q15-your-docker-compose-app-needs-to-wait-for-a-database-to-be-ready-before-starting-the-app-container-how-do-you-implement-this-l3)
22. [Docker Q16: What is Docker BuildKit and why is it better than the classic builder [L2]](#scenario-22-docker-q16-what-is-docker-buildkit-and-why-is-it-better-than-the-classic-builder-l2)
23. [Docker Q17: You need to pass a GitHub token to npm install during Docker build without it ending up in the image How [L3]](#scenario-23-docker-q17-you-need-to-pass-a-github-token-to-npm-install-during-docker-build-without-it-ending-up-in-the-image-how-l3)
24. [Docker Q18: What is the difference between docker stop and docker kill [L2]](#scenario-24-docker-q18-what-is-the-difference-between-docker-stop-and-docker-kill-l2)
25. [Docker Q19: How do you inspect a running containers environment variables and configuration [L2]](#scenario-25-docker-q19-how-do-you-inspect-a-running-containers-environment-variables-and-configuration-l2)
26. [Docker Q20: Explain Docker networking modes [L3]](#scenario-26-docker-q20-explain-docker-networking-modes-l3)
27. [Docker Q21: How do you get a shell inside a running container [L1]](#scenario-27-docker-q21-how-do-you-get-a-shell-inside-a-running-container-l1)
28. [Docker Q22: What is the difference between a Docker image and a container [L1]](#scenario-28-docker-q22-what-is-the-difference-between-a-docker-image-and-a-container-l1)
29. [Docker Q23: How do you copy a file from a container to the host [L2]](#scenario-29-docker-q23-how-do-you-copy-a-file-from-a-container-to-the-host-l2)
30. [Docker Q24: Your container image build is failing on apt-get update Whats likely wrong [L2]](#scenario-30-docker-q24-your-container-image-build-is-failing-on-apt-get-update-whats-likely-wrong-l2)
31. [Docker Q25: What is a multi-stage build and what problem does it solve [L2]](#scenario-31-docker-q25-what-is-a-multi-stage-build-and-what-problem-does-it-solve-l2)
32. [Docker Q26: How do you set environment variables when running a container [L2]](#scenario-32-docker-q26-how-do-you-set-environment-variables-when-running-a-container-l2)
33. [Docker Q27: A container writes logs to a file instead of stdout How do you collect these logs [L2]](#scenario-33-docker-q27-a-container-writes-logs-to-a-file-instead-of-stdout-how-do-you-collect-these-logs-l2)
34. [Docker Q28: How do you scan a Docker image for vulnerabilities before pushing to a registry [L3]](#scenario-34-docker-q28-how-do-you-scan-a-docker-image-for-vulnerabilities-before-pushing-to-a-registry-l3)
35. [Docker Q29: What is the purpose of dockerignore [L2]](#scenario-35-docker-q29-what-is-the-purpose-of-dockerignore-l2)
36. [Docker Q30: How do you implement health checks in Docker [L3]](#scenario-36-docker-q30-how-do-you-implement-health-checks-in-docker-l3)
37. [Docker Q31: How do you build an image for multiple CPU architectures (AMD64 and ARM64) [L2]](#scenario-37-docker-q31-how-do-you-build-an-image-for-multiple-cpu-architectures-amd64-and-arm64-l2)
38. [Docker Q32: How do you push a Docker image to a private registry [L2]](#scenario-38-docker-q32-how-do-you-push-a-docker-image-to-a-private-registry-l2)
39. [Docker Q33: What does EXPOSE do in a Dockerfile [L2]](#scenario-39-docker-q33-what-does-expose-do-in-a-dockerfile-l2)
40. [Docker Q34: How do you run Docker Compose in production [L3]](#scenario-40-docker-q34-how-do-you-run-docker-compose-in-production-l3)
41. [Docker Q35: How do you override the default CMD when running a container [L2]](#scenario-41-docker-q35-how-do-you-override-the-default-cmd-when-running-a-container-l2)
42. [Docker Q36: What is an init container (not Kubernetes) Why might you use --init in Docker [L2]](#scenario-42-docker-q36-what-is-an-init-container-not-kubernetes-why-might-you-use-init-in-docker-l2)
43. [Docker Q37: How do you debug a container that crashes before you can exec into it [L3]](#scenario-43-docker-q37-how-do-you-debug-a-container-that-crashes-before-you-can-exec-into-it-l3)
44. [Docker Q38: What is image layer caching and why does layer ORDER matter [L2]](#scenario-44-docker-q38-what-is-image-layer-caching-and-why-does-layer-order-matter-l2)
45. [Docker Q39: How do you see which processes are running inside a container [L2]](#scenario-45-docker-q39-how-do-you-see-which-processes-are-running-inside-a-container-l2)
46. [Docker Q40: Explain Docker content trust (DCT) and why it matters [L3]](#scenario-46-docker-q40-explain-docker-content-trust-dct-and-why-it-matters-l3)
47. [Docker Q41: What is a dangling image in Docker [L2]](#scenario-47-docker-q41-what-is-a-dangling-image-in-docker-l2)
48. [Docker Q42: How do you set resource limits for a Docker Compose service [L2]](#scenario-48-docker-q42-how-do-you-set-resource-limits-for-a-docker-compose-service-l2)
49. [Docker Q43: How does container networking work at the Linux kernel level [L3]](#scenario-49-docker-q43-how-does-container-networking-work-at-the-linux-kernel-level-l3)
50. [Docker Q44: How do you rebuild only a specific service in Docker Compose [L2]](#scenario-50-docker-q44-how-do-you-rebuild-only-a-specific-service-in-docker-compose-l2)
51. [Docker Q45: What is the difference between docker-compose up and docker-compose run [L2]](#scenario-51-docker-q45-what-is-the-difference-between-docker-compose-up-and-docker-compose-run-l2)
52. [Docker Q46: You need to run a container with access to the hosts Unix socket (eg Docker socket) What are the security implications [L3]](#scenario-52-docker-q46-you-need-to-run-a-container-with-access-to-the-hosts-unix-socket-eg-docker-socket-what-are-the-security-implications-l3)
53. [Docker Q47: How do you roll back to a previous Docker image version in Kubernetes [L2]](#scenario-53-docker-q47-how-do-you-roll-back-to-a-previous-docker-image-version-in-kubernetes-l2)
54. [Docker Q48: What is Docker Swarm and how does it compare to Kubernetes [L2]](#scenario-54-docker-q48-what-is-docker-swarm-and-how-does-it-compare-to-kubernetes-l2)
55. [Docker Q49: How do you optimize Docker builds in a monorepo where multiple services share code [L3]](#scenario-55-docker-q49-how-do-you-optimize-docker-builds-in-a-monorepo-where-multiple-services-share-code-l3)
56. [Docker Q50: How do you make sure containers restart on host reboot [L2]](#scenario-56-docker-q50-how-do-you-make-sure-containers-restart-on-host-reboot-l2)
57. [Docker Q51: What is the purpose of docker commit [L2]](#scenario-57-docker-q51-what-is-the-purpose-of-docker-commit-l2)
58. [Docker Q52: How do you pass build arguments (not environment variables) to a Docker build [L2]](#scenario-58-docker-q52-how-do-you-pass-build-arguments-not-environment-variables-to-a-docker-build-l2)
59. [Docker Q53: How do you implement a Docker image garbage collection policy in a registry [L3]](#scenario-59-docker-q53-how-do-you-implement-a-docker-image-garbage-collection-policy-in-a-registry-l3)
60. [Docker Q54: What does docker save and docker load do [L2]](#scenario-60-docker-q54-what-does-docker-save-and-docker-load-do-l2)
61. [Docker Q55: How do you ensure your containers run with the minimum required Linux capabilities [L3]](#scenario-61-docker-q55-how-do-you-ensure-your-containers-run-with-the-minimum-required-linux-capabilities-l3)
62. [Docker Q56: How do you view the Docker build history/layers of an image [L2]](#scenario-62-docker-q56-how-do-you-view-the-docker-build-history-layers-of-an-image-l2)
63. [Docker Q57: What is the difference between VOLUME instruction and runtime volume mount [L2]](#scenario-63-docker-q57-what-is-the-difference-between-volume-instruction-and-runtime-volume-mount-l2)
64. [Docker Q58: How do you run integration tests in CI that require real external services (Redis Kafka) using Docker [L3]](#scenario-64-docker-q58-how-do-you-run-integration-tests-in-ci-that-require-real-external-services-redis-kafka-using-docker-l3)
65. [Docker Q59: How do you debug network connectivity between two containers [L2]](#scenario-65-docker-q59-how-do-you-debug-network-connectivity-between-two-containers-l2)
66. [Docker Q60: Explain the security implications of running containers in privileged mode and when its acceptable [L3]](#scenario-66-docker-q60-explain-the-security-implications-of-running-containers-in-privileged-mode-and-when-its-acceptable-l3)
67. [Docker Q61: A junior developer complains that every time they edit a file on their host machine the changes dont physically appear inside the Docker container despite having a bind mount configured What is the most likely culprit [L2]](#scenario-67-docker-q61-a-junior-developer-complains-that-every-time-they-edit-a-file-on-their-host-machine-the-changes-dont-physically-appear-inside-the-docker-container-despite-having-a-bind-mount-configured-what-is-the-most-likely-culprit-l2)
68. [Docker Q62: You set up a strict UFW (Uncomplicated Firewall) on your Ubuntu server to block all incoming traffic to port 8080 You then run a Docker container docker run -p 808080 myapp Miraculously a hacker easily accesses your app on port 8080 from the internet Why did the firewall fail [L3]](#scenario-68-docker-q62-you-set-up-a-strict-ufw-uncomplicated-firewall-on-your-ubuntu-server-to-block-all-incoming-traffic-to-port-8080-you-then-run-a-docker-container-docker-run-p-808080-myapp-miraculously-a-hacker-easily-accesses-your-app-on-port-8080-from-the-internet-why-did-the-firewall-fail-l3)
69. [Docker Q63: A container exits with code 137 What does this specific code universally mean in the Docker ecosystem and where should you look next [L1]](#scenario-69-docker-q63-a-container-exits-with-code-137-what-does-this-specific-code-universally-mean-in-the-docker-ecosystem-and-where-should-you-look-next-l1)
70. [Docker Q64: You are tasked with debugging a critically failing production container However the container is built Distroless (it has absolutely no shell no bash no ls no curl) docker exec fails with executable file not found in $PATH How do you run debugging tools against this container [L3]](#scenario-70-docker-q64-you-are-tasked-with-debugging-a-critically-failing-production-container-however-the-container-is-built-distroless-it-has-absolutely-no-shell-no-bash-no-ls-no-curl-docker-exec-fails-with-executable-file-not-found-in-path-how-do-you-run-debugging-tools-against-this-container-l3)
71. [Docker Q65: A Python data science container parsing massive multi-gigabyte pandas dataframes suddenly crashes randomly The code is flawless the server has 128GB of RAM and OOMKilled is false You notice the crash happens specifically when multiprocessing writes heavily What hidden Docker limit is causing this [L2]](#scenario-71-docker-q65-a-python-data-science-container-parsing-massive-multi-gigabyte-pandas-dataframes-suddenly-crashes-randomly-the-code-is-flawless-the-server-has-128gb-of-ram-and-oomkilled-is-false-you-notice-the-crash-happens-specifically-when-multiprocessing-writes-heavily-what-hidden-docker-limit-is-causing-this-l2)
72. [Docker Q66: A developer submits a Dockerfile that copies a 5GB file runs a command to compress it to 100MB and then runs rm to delete the original 5GB file in the next step Why does the final Docker image still weigh over 5GB [L1]](#scenario-72-docker-q66-a-developer-submits-a-dockerfile-that-copies-a-5gb-file-runs-a-command-to-compress-it-to-100mb-and-then-runs-rm-to-delete-the-original-5gb-file-in-the-next-step-why-does-the-final-docker-image-still-weigh-over-5gb-l1)
73. [Docker Q67: Your company is migrating stateful MySQL databases to Docker A consultant advises using Bind Mounts You disagree and advocate strongly for completely bypassing the Docker Storage Driver entirely by utilizing raw Block Devices Why [L3]](#scenario-73-docker-q67-your-company-is-migrating-stateful-mysql-databases-to-docker-a-consultant-advises-using-bind-mounts-you-disagree-and-advocate-strongly-for-completely-bypassing-the-docker-storage-driver-entirely-by-utilizing-raw-block-devices-why-l3)
74. [Docker Q68: You execute docker run -d myapp The terminal returns a long container ID but immediately upon checking docker ps the container is completely missing docker ps -a shows it exited with code 0 Why did it immediately stop if it didnt error [L2]](#scenario-74-docker-q68-you-execute-docker-run-d-myapp-the-terminal-returns-a-long-container-id-but-immediately-upon-checking-docker-ps-the-container-is-completely-missing-docker-ps-a-shows-it-exited-with-code-0-why-did-it-immediately-stop-if-it-didnt-error-l2)
75. [Docker Q69: What happens if your CI pipeline repeatedly builds the exact same Dockerfile using the latest tag and pushes it to an AWS ECR registry every day for a year [L1]](#scenario-75-docker-q69-what-happens-if-your-ci-pipeline-repeatedly-builds-the-exact-same-dockerfile-using-the-latest-tag-and-pushes-it-to-an-aws-ecr-registry-every-day-for-a-year-l1)
76. [Docker Q70: You want to pass a highly sensitive API key to a running container You know not to bake it into the image so you pass it as an environment variable (docker run -e SECRET=apikey) Why is this still arguably a security vulnerability and what is the better approach [L3]](#scenario-76-docker-q70-you-want-to-pass-a-highly-sensitive-api-key-to-a-running-container-you-know-not-to-bake-it-into-the-image-so-you-pass-it-as-an-environment-variable-docker-run-e-secret-apikey-why-is-this-still-arguably-a-security-vulnerability-and-what-is-the-better-approach-l3)
77. [Docker Q71: A heavily loaded Nginx container starts rejecting connections citing Too many open files You check the host Linux server and its ulimit -n is set to 1000000 Why is the container still failing [L2]](#scenario-77-docker-q71-a-heavily-loaded-nginx-container-starts-rejecting-connections-citing-too-many-open-files-you-check-the-host-linux-server-and-its-ulimit-n-is-set-to-1000000-why-is-the-container-still-failing-l2)
78. [Docker Q72: You are investigating an incident How do you find the exact time a container was created started and stopped down to the millisecond [L1]](#scenario-78-docker-q72-you-are-investigating-an-incident-how-do-you-find-the-exact-time-a-container-was-created-started-and-stopped-down-to-the-millisecond-l1)
79. [Docker Q73: Your CI/CD builds for a massive Go monorepo are taking 20 minutes because every minor code change invalidates the RUN go mod download layer forcing a re-download of gigabytes of packages How do you optimize the Dockerfile to utilize BuildKit cache mounts and permanently speed this up [L3]](#scenario-79-docker-q73-your-ci-cd-builds-for-a-massive-go-monorepo-are-taking-20-minutes-because-every-minor-code-change-invalidates-the-run-go-mod-download-layer-forcing-a-re-download-of-gigabytes-of-packages-how-do-you-optimize-the-dockerfile-to-utilize-buildkit-cache-mounts-and-permanently-speed-this-up-l3)
80. [Docker Q74: A developer executes a docker run --rm -v /home/user/code/app mynode to run a script containing npm install When the container finishes the developer finds that all the new node_modules files placed in their /home/user/code folder are owned by root Why and how do you prevent this [L2]](#scenario-80-docker-q74-a-developer-executes-a-docker-run-rm-v-home-user-code-app-mynode-to-run-a-script-containing-npm-install-when-the-container-finishes-the-developer-finds-that-all-the-new-node-modules-files-placed-in-their-home-user-code-folder-are-owned-by-root-why-and-how-do-you-prevent-this-l2)
81. [Docker Q75: What happens if you run out of IPs in a Docker bridge network How many IPs does the default Docker bridge give you by default [L1]](#scenario-81-docker-q75-what-happens-if-you-run-out-of-ips-in-a-docker-bridge-network-how-many-ips-does-the-default-docker-bridge-give-you-by-default-l1)
82. [Docker Q76: You deploy a cluster of 50 identical microservices To ensure zero drifts they all pull a massive 1GB initial configuration file from a central S3 bucket immediately upon booting via the CMD script Why is this an anti-pattern in container architecture and what is the immutable alternative [L3]](#scenario-82-docker-q76-you-deploy-a-cluster-of-50-identical-microservices-to-ensure-zero-drifts-they-all-pull-a-massive-1gb-initial-configuration-file-from-a-central-s3-bucket-immediately-upon-booting-via-the-cmd-script-why-is-this-an-anti-pattern-in-container-architecture-and-what-is-the-immutable-alternative-l3)
83. [Docker Q77: What is a Dangling Volume and how does it happen [L2]](#scenario-83-docker-q77-what-is-a-dangling-volume-and-how-does-it-happen-l2)
84. [Docker Q78: Are Docker containers fundamentally virtual machines Defend your answer [L1]](#scenario-84-docker-q78-are-docker-containers-fundamentally-virtual-machines-defend-your-answer-l1)
85. [Docker Q79: Youve developed an internal tool specifically for your SRE team using Python Due to compliance you must heavily sign all your Docker images cryptographically to prove they originated exclusively from your exact CI/CD server before production will run them What Docker technology enforces this [L3]](#scenario-85-docker-q79-youve-developed-an-internal-tool-specifically-for-your-sre-team-using-python-due-to-compliance-you-must-heavily-sign-all-your-docker-images-cryptographically-to-prove-they-originated-exclusively-from-your-exact-ci-cd-server-before-production-will-run-them-what-docker-technology-enforces-this-l3)
86. [Docker Q80: A junior engineer asks why they cant effectively run a Windows exe binary inside a standardized Ubuntu Docker container running natively on a Windows 10 host using Docker Desktop Explain the architecture constraint [L2]](#scenario-86-docker-q80-a-junior-engineer-asks-why-they-cant-effectively-run-a-windows-exe-binary-inside-a-standardized-ubuntu-docker-container-running-natively-on-a-windows-10-host-using-docker-desktop-explain-the-architecture-constraint-l2)
87. [Docker Q81: You are running a sidecar monitoring agent alongside your main application container using Docker Compose The agent needs to see all the processes running inside the main application container using ps aux By default it can only see its own processes How do you solve this [L3]](#scenario-87-docker-q81-you-are-running-a-sidecar-monitoring-agent-alongside-your-main-application-container-using-docker-compose-the-agent-needs-to-see-all-the-processes-running-inside-the-main-application-container-using-ps-aux-by-default-it-can-only-see-its-own-processes-how-do-you-solve-this-l3)
88. [Docker Q82: A developer runs a containerized application that writes millions of tiny temporary cache files during processing After a few hours the container crashes with No space left on device even though docker stats shows plenty of disk available What is happening [L2]](#scenario-88-docker-q82-a-developer-runs-a-containerized-application-that-writes-millions-of-tiny-temporary-cache-files-during-processing-after-a-few-hours-the-container-crashes-with-no-space-left-on-device-even-though-docker-stats-shows-plenty-of-disk-available-what-is-happening-l2)
89. [Docker Q83: Your company has a local Docker registry a staging registry on GCP Artifact Registry and a production registry on AWS ECR A developer complains about constantly running docker login and docker logout to switch between them What is the cleaner approach [L2]](#scenario-89-docker-q83-your-company-has-a-local-docker-registry-a-staging-registry-on-gcp-artifact-registry-and-a-production-registry-on-aws-ecr-a-developer-complains-about-constantly-running-docker-login-and-docker-logout-to-switch-between-them-what-is-the-cleaner-approach-l2)
90. [Docker Q84: A containerized microservice makes HTTP calls to apiexamplecom It works perfectly when tested locally on a developer laptop but fails with DNS resolution errors when deployed inside a Docker container on the CI server The CI server itself can resolve the domain fine What is wrong [L2]](#scenario-90-docker-q84-a-containerized-microservice-makes-http-calls-to-apiexamplecom-it-works-perfectly-when-tested-locally-on-a-developer-laptop-but-fails-with-dns-resolution-errors-when-deployed-inside-a-docker-container-on-the-ci-server-the-ci-server-itself-can-resolve-the-domain-fine-what-is-wrong-l2)
91. [Docker Q85: After months of daily Docker builds your production servers disk is full You run docker system prune -af and reclaim some space but the disk is still 90% full docker system df shows minimal usage Where is the hidden disk consumption [L3]](#scenario-91-docker-q85-after-months-of-daily-docker-builds-your-production-servers-disk-is-full-you-run-docker-system-prune-af-and-reclaim-some-space-but-the-disk-is-still-90-full-docker-system-df-shows-minimal-usage-where-is-the-hidden-disk-consumption-l3)
92. [Docker Q86: Your security team mandates that Docker must run without root privileges on all developer workstations The developers still need full Docker build and run capabilities How do you achieve this [L3]](#scenario-92-docker-q86-your-security-team-mandates-that-docker-must-run-without-root-privileges-on-all-developer-workstations-the-developers-still-need-full-docker-build-and-run-capabilities-how-do-you-achieve-this-l3)
93. [Docker Q87: Your CI pipeline runs unit tests inside a Docker build using a multi-stage Dockerfile If the tests fail you want to extract the test report (JUnit XML) from the failed build stage But docker build exits with an error and produces no final image How do you get the test report out [L2]](#scenario-93-docker-q87-your-ci-pipeline-runs-unit-tests-inside-a-docker-build-using-a-multi-stage-dockerfile-if-the-tests-fail-you-want-to-extract-the-test-report-junit-xml-from-the-failed-build-stage-but-docker-build-exits-with-an-error-and-produces-no-final-image-how-do-you-get-the-test-report-out-l2)
94. [Docker Q88: A production container running an API gateway is performing well but you notice its writable layer is growing by 500MB per day The application itself doesnt write data to disk intentionally What is causing the growth and how do you stop it [L2]](#scenario-94-docker-q88-a-production-container-running-an-api-gateway-is-performing-well-but-you-notice-its-writable-layer-is-growing-by-500mb-per-day-the-application-itself-doesnt-write-data-to-disk-intentionally-what-is-causing-the-growth-and-how-do-you-stop-it-l2)
95. [Docker Q89: Your CI pipeline runs Dockerized build jobs that themselves need to build Docker images (Docker-in-Docker) The team currently mounts the host Docker socket (/var/run/dockersock) The security team rejects this What are the alternatives [L3]](#scenario-95-docker-q89-your-ci-pipeline-runs-dockerized-build-jobs-that-themselves-need-to-build-docker-images-docker-in-docker-the-team-currently-mounts-the-host-docker-socket-var-run-dockersock-the-security-team-rejects-this-what-are-the-alternatives-l3)
96. [Docker Q90: A container running Nginx generates enormous log files and eventually fills the disk on the Docker host You want Docker to automatically handle log rotation without modifying the Nginx configuration How [L2]](#scenario-96-docker-q90-a-container-running-nginx-generates-enormous-log-files-and-eventually-fills-the-disk-on-the-docker-host-you-want-docker-to-automatically-handle-log-rotation-without-modifying-the-nginx-configuration-how-l2)
97. [Docker Q91: You deploy a financial application container and the compliance team requires that the containers filesystem must be completely immutable at runtime — no process should be able to write anywhere except explicitly approved paths How do you enforce this [L3]](#scenario-97-docker-q91-you-deploy-a-financial-application-container-and-the-compliance-team-requires-that-the-containers-filesystem-must-be-completely-immutable-at-runtime-no-process-should-be-able-to-write-anywhere-except-explicitly-approved-paths-how-do-you-enforce-this-l3)
98. [Docker Q92: Your team wants to implement live migration of a running Docker container from one host to another without stopping it similar to VM live migration Is this possible with Docker What technology enables it [L3]](#scenario-98-docker-q92-your-team-wants-to-implement-live-migration-of-a-running-docker-container-from-one-host-to-another-without-stopping-it-similar-to-vm-live-migration-is-this-possible-with-docker-what-technology-enables-it-l3)
99. [Docker Q93: A developer has a project with a 10GB data/ directory containing training datasets Every docker build takes 15 minutes before even executing the first Dockerfile instruction The Dockerfile doesnt reference the data/ directory at all Why is it so slow [L2]](#scenario-99-docker-q93-a-developer-has-a-project-with-a-10gb-data-directory-containing-training-datasets-every-docker-build-takes-15-minutes-before-even-executing-the-first-dockerfile-instruction-the-dockerfile-doesnt-reference-the-data-directory-at-all-why-is-it-so-slow-l2)
100. [Docker Q94: Your Docker Compose file defines 15 services but during local development you only need 4 of them running Starting all 15 wastes resources and slows down your machine How do you selectively start subsets of services without maintaining multiple Compose files [L2]](#scenario-100-docker-q94-your-docker-compose-file-defines-15-services-but-during-local-development-you-only-need-4-of-them-running-starting-all-15-wastes-resources-and-slows-down-your-machine-how-do-you-selectively-start-subsets-of-services-without-maintaining-multiple-compose-files-l2)
101. [Docker Q95: A containerized application needs to call an API server running directly on the Docker host machine (not in a container) Using localhost or 127001 from inside the container doesnt work How does the container reach the host [L2]](#scenario-101-docker-q95-a-containerized-application-needs-to-call-an-api-server-running-directly-on-the-docker-host-machine-not-in-a-container-using-localhost-or-127001-from-inside-the-container-doesnt-work-how-does-the-container-reach-the-host-l2)
102. [Docker Q96: Your CI pipeline suddenly starts failing with toomanyrequests You have reached your pull rate limit errors when pulling base images from Docker Hub What is happening and how do you fix it [L2]](#scenario-102-docker-q96-your-ci-pipeline-suddenly-starts-failing-with-toomanyrequests-you-have-reached-your-pull-rate-limit-errors-when-pulling-base-images-from-docker-hub-what-is-happening-and-how-do-you-fix-it-l2)
103. [Docker Q97: You need to verify whether a Docker image tagged myappv210 in your registry is truly a multi-architecture image that supports both linux/amd64 and linux/arm64 without pulling the entire image How do you inspect this remotely [L3]](#scenario-103-docker-q97-you-need-to-verify-whether-a-docker-image-tagged-myappv210-in-your-registry-is-truly-a-multi-architecture-image-that-supports-both-linux-amd64-and-linux-arm64-without-pulling-the-entire-image-how-do-you-inspect-this-remotely-l3)
104. [Docker Q98: You run a shell script as the ENTRYPOINT that spawns multiple background worker processes When you docker stop the container it always takes exactly 10 seconds (the timeout) before stopping and the workers dont clean up properly What is the root cause [L2]](#scenario-104-docker-q98-you-run-a-shell-script-as-the-entrypoint-that-spawns-multiple-background-worker-processes-when-you-docker-stop-the-container-it-always-takes-exactly-10-seconds-the-timeout-before-stopping-and-the-workers-dont-clean-up-properly-what-is-the-root-cause-l2)
105. [Docker Q99: After a container has been running for several days you want to see exactly what files were added modified or deleted inside the container compared to its original image How do you do this without stopping the container [L2]](#scenario-105-docker-q99-after-a-container-has-been-running-for-several-days-you-want-to-see-exactly-what-files-were-added-modified-or-deleted-inside-the-container-compared-to-its-original-image-how-do-you-do-this-without-stopping-the-container-l2)
106. [Docker Q100: You have two containers on the same Docker network Container A needs to reach Container B but Container Bs name is a long auto-generated string like project_backend_service_1 You want a shorter more memorable hostname How do you assign one without renaming the container [L2]](#scenario-106-docker-q100-you-have-two-containers-on-the-same-docker-network-container-a-needs-to-reach-container-b-but-container-bs-name-is-a-long-auto-generated-string-like-project-backend-service-1-you-want-a-shorter-more-memorable-hostname-how-do-you-assign-one-without-renaming-the-container-l2)
107. [Kubernetes Q1: Your pod is stuck in Pending state What do you do [L1]](#scenario-107-kubernetes-q1-your-pod-is-stuck-in-pending-state-what-do-you-do-l1)
108. [Kubernetes Q2: A pod is in CrashLoopBackOff How do you debug it [L1]](#scenario-108-kubernetes-q2-a-pod-is-in-crashloopbackoff-how-do-you-debug-it-l1)
109. [Kubernetes Q3: A pod shows OOMKilled in its status What happened and how do you fix it [L2]](#scenario-109-kubernetes-q3-a-pod-shows-oomkilled-in-its-status-what-happened-and-how-do-you-fix-it-l2)
110. [Kubernetes Q4: Your deployment rollout is stuck Pods from the new version arent coming up but old ones are still running Whats happening [L2]](#scenario-110-kubernetes-q4-your-deployment-rollout-is-stuck-pods-from-the-new-version-arent-coming-up-but-old-ones-are-still-running-whats-happening-l2)
111. [Kubernetes Q5: A pod is Running but your app is not reachable via the Service What do you check [L2]](#scenario-111-kubernetes-q5-a-pod-is-running-but-your-app-is-not-reachable-via-the-service-what-do-you-check-l2)
112. [Kubernetes Q6: A node in your cluster shows NotReady Your team is panicking because several services are on it Whats your action plan [L3]](#scenario-112-kubernetes-q6-a-node-in-your-cluster-shows-notready-your-team-is-panicking-because-several-services-are-on-it-whats-your-action-plan-l3)
113. [Kubernetes Q7: Your HPA (Horizontal Pod Autoscaler) is not scaling up even though CPU usage is high Why [L2]](#scenario-113-kubernetes-q7-your-hpa-horizontal-pod-autoscaler-is-not-scaling-up-even-though-cpu-usage-is-high-why-l2)
114. [Kubernetes Q8: A pod has been running fine for weeks and suddenly starts failing with ImagePullBackOff Nothing in the pod spec changed What could cause this [L3]](#scenario-114-kubernetes-q8-a-pod-has-been-running-fine-for-weeks-and-suddenly-starts-failing-with-imagepullbackoff-nothing-in-the-pod-spec-changed-what-could-cause-this-l3)
115. [Kubernetes Q9: You run kubectl exec -it <pod> -- bash and get container not found Whats wrong [L2]](#scenario-115-kubernetes-q9-you-run-kubectl-exec-it-pod-bash-and-get-container-not-found-whats-wrong-l2)
116. [Kubernetes Q10: Your init container is stuck and the main container never starts How do you debug [L2]](#scenario-116-kubernetes-q10-your-init-container-is-stuck-and-the-main-container-never-starts-how-do-you-debug-l2)
117. [Kubernetes Q11: Whats the difference between a Deployment and a StatefulSet When would you use each [L1]](#scenario-117-kubernetes-q11-whats-the-difference-between-a-deployment-and-a-statefulset-when-would-you-use-each-l1)
118. [Kubernetes Q12: You need to run a database in Kubernetes Someone says just use a Deployment with a PVC Is that okay [L2]](#scenario-118-kubernetes-q12-you-need-to-run-a-database-in-kubernetes-someone-says-just-use-a-deployment-with-a-pvc-is-that-okay-l2)
119. [Kubernetes Q13: You updated a ConfigMap thats mounted as an environment variable in a pod The pod still shows the old value Why [L2]](#scenario-119-kubernetes-q13-you-updated-a-configmap-thats-mounted-as-an-environment-variable-in-a-pod-the-pod-still-shows-the-old-value-why-l2)
120. [Kubernetes Q14: How would you ensure a critical pod always runs on the same node [L2]](#scenario-120-kubernetes-q14-how-would-you-ensure-a-critical-pod-always-runs-on-the-same-node-l2)
121. [Kubernetes Q15: You want to make sure two pods of the same app NEVER run on the same node How [L2]](#scenario-121-kubernetes-q15-you-want-to-make-sure-two-pods-of-the-same-app-never-run-on-the-same-node-how-l2)
122. [Kubernetes Q16: Your deployment has 10 replicas You need to do a zero-downtime deploy of a new version How do you configure and verify it [L3]](#scenario-122-kubernetes-q16-your-deployment-has-10-replicas-you-need-to-do-a-zero-downtime-deploy-of-a-new-version-how-do-you-configure-and-verify-it-l3)
123. [Kubernetes Q17: What is a DaemonSet and when do you use it [L1]](#scenario-123-kubernetes-q17-what-is-a-daemonset-and-when-do-you-use-it-l1)
124. [Kubernetes Q18: You have a DaemonSet but some nodes arent getting a pod Why [L2]](#scenario-124-kubernetes-q18-you-have-a-daemonset-but-some-nodes-arent-getting-a-pod-why-l2)
125. [Kubernetes Q19: When would you use a Job vs a CronJob [L2]](#scenario-125-kubernetes-q19-when-would-you-use-a-job-vs-a-cronjob-l2)
126. [Kubernetes Q20: Your CronJob is creating overlapping runs — the previous job hasnt finished when the next one starts How do you fix it [L2]](#scenario-126-kubernetes-q20-your-cronjob-is-creating-overlapping-runs-the-previous-job-hasnt-finished-when-the-next-one-starts-how-do-you-fix-it-l2)
127. [Kubernetes Q21: What is the difference between ClusterIP NodePort and LoadBalancer service types [L1]](#scenario-127-kubernetes-q21-what-is-the-difference-between-clusterip-nodeport-and-loadbalancer-service-types-l1)
128. [Kubernetes Q22: What is an Ingress and why do you need it when you already have LoadBalancer services [L2]](#scenario-128-kubernetes-q22-what-is-an-ingress-and-why-do-you-need-it-when-you-already-have-loadbalancer-services-l2)
129. [Kubernetes Q23: Your Ingress is returning 404 for a path that youve configured What do you check [L2]](#scenario-129-kubernetes-q23-your-ingress-is-returning-404-for-a-path-that-youve-configured-what-do-you-check-l2)
130. [Kubernetes Q24: You have a microservices app where Service A should never talk directly to Service C only through Service B How do you enforce this in Kubernetes [L3]](#scenario-130-kubernetes-q24-you-have-a-microservices-app-where-service-a-should-never-talk-directly-to-service-c-only-through-service-b-how-do-you-enforce-this-in-kubernetes-l3)
131. [Kubernetes Q25: What is a headless service and why would you use it [L2]](#scenario-131-kubernetes-q25-what-is-a-headless-service-and-why-would-you-use-it-l2)
132. [Kubernetes Q26: A request is going from Pod A to Pod B via a Service and its very slow How do you troubleshoot network latency in Kubernetes [L3]](#scenario-132-kubernetes-q26-a-request-is-going-from-pod-a-to-pod-b-via-a-service-and-its-very-slow-how-do-you-troubleshoot-network-latency-in-kubernetes-l3)
133. [Kubernetes Q27: DNS resolution is failing inside your cluster Pods cant resolve service names What do you check [L2]](#scenario-133-kubernetes-q27-dns-resolution-is-failing-inside-your-cluster-pods-cant-resolve-service-names-what-do-you-check-l2)
134. [Kubernetes Q28: What is the difference between a PersistentVolume (PV) and a PersistentVolumeClaim (PVC) [L1]](#scenario-134-kubernetes-q28-what-is-the-difference-between-a-persistentvolume-pv-and-a-persistentvolumeclaim-pvc-l1)
135. [Kubernetes Q29: A PVC is stuck in Pending state What do you check [L2]](#scenario-135-kubernetes-q29-a-pvc-is-stuck-in-pending-state-what-do-you-check-l2)
136. [Kubernetes Q30: You deleted a PVC but the data is gone How could you have protected it [L2]](#scenario-136-kubernetes-q30-you-deleted-a-pvc-but-the-data-is-gone-how-could-you-have-protected-it-l2)
137. [Kubernetes Q31: A StatefulSet pod cant start because its trying to attach a volume thats still attached to a terminated pod on a dead node How do you fix it [L3]](#scenario-137-kubernetes-q31-a-statefulset-pod-cant-start-because-its-trying-to-attach-a-volume-thats-still-attached-to-a-terminated-pod-on-a-dead-node-how-do-you-fix-it-l3)
138. [Kubernetes Q32: A developer says they cant list pods in the production namespace but they can in staging How do you debug this [L2]](#scenario-138-kubernetes-q32-a-developer-says-they-cant-list-pods-in-the-production-namespace-but-they-can-in-staging-how-do-you-debug-this-l2)
139. [Kubernetes Q33: You run a pod that needs to call the Kubernetes API (eg to list other pods) How do you set this up securely [L2]](#scenario-139-kubernetes-q33-you-run-a-pod-that-needs-to-call-the-kubernetes-api-eg-to-list-other-pods-how-do-you-set-this-up-securely-l2)
140. [Kubernetes Q34: Someone accidentally ran kubectl delete clusterrolebinding cluster-admin and deleted the cluster admin binding Now no one can manage the cluster What do you do [L3]](#scenario-140-kubernetes-q34-someone-accidentally-ran-kubectl-delete-clusterrolebinding-cluster-admin-and-deleted-the-cluster-admin-binding-now-no-one-can-manage-the-cluster-what-do-you-do-l3)
141. [Kubernetes Q35: Your app gets a traffic spike every day at 9 AM when offices open HPA isnt fast enough What do you do [L2]](#scenario-141-kubernetes-q35-your-app-gets-a-traffic-spike-every-day-at-9-am-when-offices-open-hpa-isnt-fast-enough-what-do-you-do-l2)
142. [Kubernetes Q36: HPA is scaling pods up and down too aggressively causing instability How do you fix it [L2]](#scenario-142-kubernetes-q36-hpa-is-scaling-pods-up-and-down-too-aggressively-causing-instability-how-do-you-fix-it-l2)
143. [Kubernetes Q37: Your cluster has 50 nodes and pod scheduling is taking 10+ seconds What could cause this and how do you fix it [L3]](#scenario-143-kubernetes-q37-your-cluster-has-50-nodes-and-pod-scheduling-is-taking-10-seconds-what-could-cause-this-and-how-do-you-fix-it-l3)
144. [Kubernetes Q38: You need to run a privileged pod that can modify kernel parameters on the host How do you do this and what are the security implications [L3]](#scenario-144-kubernetes-q38-you-need-to-run-a-privileged-pod-that-can-modify-kernel-parameters-on-the-host-how-do-you-do-this-and-what-are-the-security-implications-l3)
145. [Kubernetes Q39: You need to do a zero-downtime migration of a StatefulSet (eg upgrading Postgres version) Walk me through your approach [L3]](#scenario-145-kubernetes-q39-you-need-to-do-a-zero-downtime-migration-of-a-statefulset-eg-upgrading-postgres-version-walk-me-through-your-approach-l3)
146. [Kubernetes Q40: Your team wants to implement GitOps for Kubernetes What tools would you recommend and what does the workflow look like [L3]](#scenario-146-kubernetes-q40-your-team-wants-to-implement-gitops-for-kubernetes-what-tools-would-you-recommend-and-what-does-the-workflow-look-like-l3)
147. [Kubernetes Q41: How do you handle secrets in Kubernetes What are the problems with default Kubernetes Secrets [L2]](#scenario-147-kubernetes-q41-how-do-you-handle-secrets-in-kubernetes-what-are-the-problems-with-default-kubernetes-secrets-l2)
148. [Kubernetes Q42: A developer wants to test a microservice that depends on 8 other services Setting up the full cluster locally is impractical What would you suggest [L3]](#scenario-148-kubernetes-q42-a-developer-wants-to-test-a-microservice-that-depends-on-8-other-services-setting-up-the-full-cluster-locally-is-impractical-what-would-you-suggest-l3)
149. [Kubernetes Q43: Your cluster upgrade from 126 to 127 failed halfway through Control plane is on 127 but worker nodes are still on 126 Is this okay [L2]](#scenario-149-kubernetes-q43-your-cluster-upgrade-from-126-to-127-failed-halfway-through-control-plane-is-on-127-but-worker-nodes-are-still-on-126-is-this-okay-l2)
150. [Kubernetes Q44: How do you handle configuration that differs between environments (dev staging prod) in Kubernetes [L2]](#scenario-150-kubernetes-q44-how-do-you-handle-configuration-that-differs-between-environments-dev-staging-prod-in-kubernetes-l2)
151. [Kubernetes Q45: You want to implement pod disruption budgets across your cluster What is a PDB and how does it protect your services [L3]](#scenario-151-kubernetes-q45-you-want-to-implement-pod-disruption-budgets-across-your-cluster-what-is-a-pdb-and-how-does-it-protect-your-services-l3)
152. [Kubernetes Q46: What happens to pods when you run kubectl drain on a node [L2]](#scenario-152-kubernetes-q46-what-happens-to-pods-when-you-run-kubectl-drain-on-a-node-l2)
153. [Kubernetes Q47: Explain how the Kubernetes scheduler makes a placement decision for a new pod [L3]](#scenario-153-kubernetes-q47-explain-how-the-kubernetes-scheduler-makes-a-placement-decision-for-a-new-pod-l3)
154. [Kubernetes Q48: What is a LimitRange and why would you use it [L2]](#scenario-154-kubernetes-q48-what-is-a-limitrange-and-why-would-you-use-it-l2)
155. [Kubernetes Q49: You have a multi-tenant cluster where different teams share the cluster How do you isolate them [L3]](#scenario-155-kubernetes-q49-you-have-a-multi-tenant-cluster-where-different-teams-share-the-cluster-how-do-you-isolate-them-l3)
156. [Kubernetes Q50: Explain the difference between kubectl apply and kubectl create When would you use each [L3]](#scenario-156-kubernetes-q50-explain-the-difference-between-kubectl-apply-and-kubectl-create-when-would-you-use-each-l3)
157. [Kubernetes Q51: Your readiness probe keeps failing even though the app is working fine What could be wrong [L2]](#scenario-157-kubernetes-q51-your-readiness-probe-keeps-failing-even-though-the-app-is-working-fine-what-could-be-wrong-l2)
158. [Kubernetes Q52: What is the difference between liveness and readiness probes Give a scenario where each is important [L2]](#scenario-158-kubernetes-q52-what-is-the-difference-between-liveness-and-readiness-probes-give-a-scenario-where-each-is-important-l2)
159. [Kubernetes Q53: Describe the pod lifecycle from kubectl apply to the app serving traffic [L3]](#scenario-159-kubernetes-q53-describe-the-pod-lifecycle-from-kubectl-apply-to-the-app-serving-traffic-l3)
160. [Kubernetes Q54: Someone applied a bad NetworkPolicy thats blocking all traffic in the cluster How do you recover [L2]](#scenario-160-kubernetes-q54-someone-applied-a-bad-networkpolicy-thats-blocking-all-traffic-in-the-cluster-how-do-you-recover-l2)
161. [Kubernetes Q55: What is the role of etcd in Kubernetes and what happens if etcd goes down [L3]](#scenario-161-kubernetes-q55-what-is-the-role-of-etcd-in-kubernetes-and-what-happens-if-etcd-goes-down-l3)
162. [Kubernetes Q56: How do you pass sensitive configuration (like DB passwords) to a pod without hardcoding them [L2]](#scenario-162-kubernetes-q56-how-do-you-pass-sensitive-configuration-like-db-passwords-to-a-pod-without-hardcoding-them-l2)
163. [Kubernetes Q57: You need to run a pod that requires access to the host network (like a network monitoring tool) How do you configure this [L3]](#scenario-163-kubernetes-q57-you-need-to-run-a-pod-that-requires-access-to-the-host-network-like-a-network-monitoring-tool-how-do-you-configure-this-l3)
164. [Kubernetes Q58: Explain the concept of resource requests vs limits What happens if you only set limits and not requests [L2]](#scenario-164-kubernetes-q58-explain-the-concept-of-resource-requests-vs-limits-what-happens-if-you-only-set-limits-and-not-requests-l2)
165. [Kubernetes Q59: What are the three QoS classes in Kubernetes and how does each affect eviction [L3]](#scenario-165-kubernetes-q59-what-are-the-three-qos-classes-in-kubernetes-and-how-does-each-affect-eviction-l3)
166. [Kubernetes Q60: You have a multi-container pod (sidecar pattern) How do the containers share data with each other [L2]](#scenario-166-kubernetes-q60-you-have-a-multi-container-pod-sidecar-pattern-how-do-the-containers-share-data-with-each-other-l2)
167. [Kubernetes Q61: What is the difference between emptyDir and hostPath volumes [L2]](#scenario-167-kubernetes-q61-what-is-the-difference-between-emptydir-and-hostpath-volumes-l2)
168. [Kubernetes Q62: A cluster-autoscaler is not scaling up even though pods are Pending What could be wrong [L3]](#scenario-168-kubernetes-q62-a-cluster-autoscaler-is-not-scaling-up-even-though-pods-are-pending-what-could-be-wrong-l3)
169. [Kubernetes Q63: How do you roll back a Helm release [L2]](#scenario-169-kubernetes-q63-how-do-you-roll-back-a-helm-release-l2)
170. [Kubernetes Q64: What is Helm and why is it used instead of raw YAML [L2]](#scenario-170-kubernetes-q64-what-is-helm-and-why-is-it-used-instead-of-raw-yaml-l2)
171. [Kubernetes Q65: Explain how Kubernetes handles pod eviction during node memory pressure [L3]](#scenario-171-kubernetes-q65-explain-how-kubernetes-handles-pod-eviction-during-node-memory-pressure-l3)
172. [Kubernetes Q66: What is the purpose of terminationGracePeriodSeconds [L2]](#scenario-172-kubernetes-q66-what-is-the-purpose-of-terminationgraceperiodseconds-l2)
173. [Kubernetes Q67: You need to run a pod that will only start after a specific ConfigMap exists in the cluster How do you implement this [L3]](#scenario-173-kubernetes-q67-you-need-to-run-a-pod-that-will-only-start-after-a-specific-configmap-exists-in-the-cluster-how-do-you-implement-this-l3)
174. [Kubernetes Q68: What is the purpose of podAntiAffinity with topologyKey topologykubernetesio/zone [L2]](#scenario-174-kubernetes-q68-what-is-the-purpose-of-podantiaffinity-with-topologykey-topologykubernetesio-zone-l2)
175. [Kubernetes Q69: Describe the Container Storage Interface (CSI) and why it replaced in-tree volume plugins [L3]](#scenario-175-kubernetes-q69-describe-the-container-storage-interface-csi-and-why-it-replaced-in-tree-volume-plugins-l3)
176. [Kubernetes Q70: What is a mutating admission webhook and give a practical use case [L3]](#scenario-176-kubernetes-q70-what-is-a-mutating-admission-webhook-and-give-a-practical-use-case-l3)
177. [Kubernetes Q71: Pod shows ErrImagePull [L1]](#scenario-177-kubernetes-q71-pod-shows-errimagepull-l1)
178. [Kubernetes Q72: Deployment has 0 ready pods but desired is 3 [L2]](#scenario-178-kubernetes-q72-deployment-has-0-ready-pods-but-desired-is-3-l2)
179. [Kubernetes Q73: How do you scale a deployment to 5 replicas [L1]](#scenario-179-kubernetes-q73-how-do-you-scale-a-deployment-to-5-replicas-l1)
180. [Kubernetes Q74: NodePort service not reachable from outside [L2]](#scenario-180-kubernetes-q74-nodeport-service-not-reachable-from-outside-l2)
181. [Kubernetes Q75: Two pods cant communicate even though NetworkPolicy allows it [L2]](#scenario-181-kubernetes-q75-two-pods-cant-communicate-even-though-networkpolicy-allows-it-l2)
182. [Kubernetes Q76: How do you upgrade Kubernetes version with zero downtime [L3]](#scenario-182-kubernetes-q76-how-do-you-upgrade-kubernetes-version-with-zero-downtime-l3)
183. [Kubernetes Q77: Ingress shows Address <pending> [L2]](#scenario-183-kubernetes-q77-ingress-shows-address-pending-l2)
184. [Kubernetes Q78: How do you get logs from all pods of a deployment [L1]](#scenario-184-kubernetes-q78-how-do-you-get-logs-from-all-pods-of-a-deployment-l1)
185. [Kubernetes Q79: Horizontal Pod Autoscaler shows unknown/50% for current metric [L2]](#scenario-185-kubernetes-q79-horizontal-pod-autoscaler-shows-unknown-50-for-current-metric-l2)
186. [Kubernetes Q80: etcd backup failed Recovery steps [L3]](#scenario-186-kubernetes-q80-etcd-backup-failed-recovery-steps-l3)
187. [Kubernetes Q81: A developer accidentally deleted a namespace How do you recover [L2]](#scenario-187-kubernetes-q81-a-developer-accidentally-deleted-a-namespace-how-do-you-recover-l2)
188. [Kubernetes Q82: Pod shows Terminating for hours and wont delete [L2]](#scenario-188-kubernetes-q82-pod-shows-terminating-for-hours-and-wont-delete-l2)
189. [Kubernetes Q83: Service mesh vs NetworkPolicy — when do you use each [L3]](#scenario-189-kubernetes-q83-service-mesh-vs-networkpolicy-when-do-you-use-each-l3)
190. [Kubernetes Q84: How do you make a pod restart on config change without a code change [L2]](#scenario-190-kubernetes-q84-how-do-you-make-a-pod-restart-on-config-change-without-a-code-change-l2)
191. [Kubernetes Q85: A CronJob job ran but the pod isnt showing in kubectl get jobs [L2]](#scenario-191-kubernetes-q85-a-cronjob-job-ran-but-the-pod-isnt-showing-in-kubectl-get-jobs-l2)
192. [Kubernetes Q86: Your admission webhook is blocking all pod creation cluster-wide How do you recover [L3]](#scenario-192-kubernetes-q86-your-admission-webhook-is-blocking-all-pod-creation-cluster-wide-how-do-you-recover-l3)
193. [Kubernetes Q87: How do you check if a service account has permission to create pods [L2]](#scenario-193-kubernetes-q87-how-do-you-check-if-a-service-account-has-permission-to-create-pods-l2)
194. [Kubernetes Q88: What is the difference between kubectl get and kubectl describe [L1]](#scenario-194-kubernetes-q88-what-is-the-difference-between-kubectl-get-and-kubectl-describe-l1)
195. [Kubernetes Q89: You want to run a one-off debug pod on a specific node How [L2]](#scenario-195-kubernetes-q89-you-want-to-run-a-one-off-debug-pod-on-a-specific-node-how-l2)
196. [Kubernetes Q90: Explain how kube-proxy implements Services using iptables [L3]](#scenario-196-kubernetes-q90-explain-how-kube-proxy-implements-services-using-iptables-l3)
197. [Kubernetes Q91: What is topology spread constraints and when would you use it over pod anti-affinity [L2]](#scenario-197-kubernetes-q91-what-is-topology-spread-constraints-and-when-would-you-use-it-over-pod-anti-affinity-l2)
198. [Kubernetes Q92: A pod needs GPU resources How do you configure it [L2]](#scenario-198-kubernetes-q92-a-pod-needs-gpu-resources-how-do-you-configure-it-l2)
199. [Kubernetes Q93: Describe leader election in Kubernetes control plane components [L3]](#scenario-199-kubernetes-q93-describe-leader-election-in-kubernetes-control-plane-components-l3)
200. [Kubernetes Q94: What is a finalizer and when would you use one [L2]](#scenario-200-kubernetes-q94-what-is-a-finalizer-and-when-would-you-use-one-l2)
201. [Kubernetes Q95: How does the Kubernetes garbage collector work [L3]](#scenario-201-kubernetes-q95-how-does-the-kubernetes-garbage-collector-work-l3)
202. [Kubernetes Q96: How do you run a privileged debug container on a running pod without modifying the pod spec [L2]](#scenario-202-kubernetes-q96-how-do-you-run-a-privileged-debug-container-on-a-running-pod-without-modifying-the-pod-spec-l2)
203. [Kubernetes Q97: What is the Kubernetes watch mechanism and how do informers use it [L3]](#scenario-203-kubernetes-q97-what-is-the-kubernetes-watch-mechanism-and-how-do-informers-use-it-l3)
204. [Kubernetes Q98: Explain the difference between kubectl apply with a file vs kubectl apply -k (kustomize) [L2]](#scenario-204-kubernetes-q98-explain-the-difference-between-kubectl-apply-with-a-file-vs-kubectl-apply-k-kustomize-l2)
205. [Kubernetes Q99: How would you migrate a stateful workload from one Kubernetes cluster to another with minimal downtime [L3]](#scenario-205-kubernetes-q99-how-would-you-migrate-a-stateful-workload-from-one-kubernetes-cluster-to-another-with-minimal-downtime-l3)
206. [Kubernetes Q100: What is KEDA and how does it extend HPA [L3]](#scenario-206-kubernetes-q100-what-is-keda-and-how-does-it-extend-hpa-l3)
207. [Kubernetes Q101: How do you expose a gRPC service in Kubernetes [L2]](#scenario-207-kubernetes-q101-how-do-you-expose-a-grpc-service-in-kubernetes-l2)
208. [Kubernetes Q102: Explain how Kubernetes handles rolling back a DaemonSet update [L3]](#scenario-208-kubernetes-q102-explain-how-kubernetes-handles-rolling-back-a-daemonset-update-l3)
209. [Kubernetes Q103: A Kubernetes Job is stuck at 0/1 Running and never starts What do you check [L2]](#scenario-209-kubernetes-q103-a-kubernetes-job-is-stuck-at-0-1-running-and-never-starts-what-do-you-check-l2)
210. [Kubernetes Q104: How do you configure a pod to get secrets from HashiCorp Vault without modifying app code [L2]](#scenario-210-kubernetes-q104-how-do-you-configure-a-pod-to-get-secrets-from-hashicorp-vault-without-modifying-app-code-l2)
211. [Kubernetes Q105: What is the Kubernetes control loop and how does it apply to custom operators [L3]](#scenario-211-kubernetes-q105-what-is-the-kubernetes-control-loop-and-how-does-it-apply-to-custom-operators-l3)
212. [Kubernetes Q106: How do you restrict a pod from accessing the cloud metadata endpoint (eg 169254169254) [L2]](#scenario-212-kubernetes-q106-how-do-you-restrict-a-pod-from-accessing-the-cloud-metadata-endpoint-eg-169254169254-l2)
213. [Kubernetes Q107: What is a ServiceAccount token and when does it expire [L2]](#scenario-213-kubernetes-q107-what-is-a-serviceaccount-token-and-when-does-it-expire-l2)
214. [Kubernetes Q108: Explain Kubernetes Operator pattern vs Helm chart When would you build an Operator [L3]](#scenario-214-kubernetes-q108-explain-kubernetes-operator-pattern-vs-helm-chart-when-would-you-build-an-operator-l3)
215. [Kubernetes Q109: How do you do a canary deployment on Kubernetes without a service mesh [L2]](#scenario-215-kubernetes-q109-how-do-you-do-a-canary-deployment-on-kubernetes-without-a-service-mesh-l2)
216. [Kubernetes Q110: What is the purpose of the kube-proxy and what happens if it goes down [L3]](#scenario-216-kubernetes-q110-what-is-the-purpose-of-the-kube-proxy-and-what-happens-if-it-goes-down-l3)
217. [Kubernetes Q111: How do you share a single Nginx config across multiple pods [L2]](#scenario-217-kubernetes-q111-how-do-you-share-a-single-nginx-config-across-multiple-pods-l2)
218. [Kubernetes Q112: What is Pod Topology Spread Constraints and how is it different from podAntiAffinity [L3]](#scenario-218-kubernetes-q112-what-is-pod-topology-spread-constraints-and-how-is-it-different-from-podantiaffinity-l3)
219. [Kubernetes Q113: How do you implement health checks for a gRPC service in Kubernetes [L2]](#scenario-219-kubernetes-q113-how-do-you-implement-health-checks-for-a-grpc-service-in-kubernetes-l2)
220. [Kubernetes Q114: Describe how Kubernetes implements Services using IPVS mode instead of iptables [L3]](#scenario-220-kubernetes-q114-describe-how-kubernetes-implements-services-using-ipvs-mode-instead-of-iptables-l3)
221. [Kubernetes Q115: You have a Kubernetes cluster in two regions for disaster recovery How do you sync workloads [L2]](#scenario-221-kubernetes-q115-you-have-a-kubernetes-cluster-in-two-regions-for-disaster-recovery-how-do-you-sync-workloads-l2)
222. [Kubernetes Q116: What is the Container Runtime Interface (CRI) and what runtimes are commonly used [L3]](#scenario-222-kubernetes-q116-what-is-the-container-runtime-interface-cri-and-what-runtimes-are-commonly-used-l3)
223. [Kubernetes Q117: How do you implement autoscaling based on custom metrics (eg queue depth) [L2]](#scenario-223-kubernetes-q117-how-do-you-implement-autoscaling-based-on-custom-metrics-eg-queue-depth-l2)
224. [Kubernetes Q118: A pod is being scheduled and then immediately evicted Whats happening [L2]](#scenario-224-kubernetes-q118-a-pod-is-being-scheduled-and-then-immediately-evicted-whats-happening-l2)
225. [Kubernetes Q119: How do you implement multi-cluster service discovery so Service A in cluster 1 can call Service B in cluster 2 [L3]](#scenario-225-kubernetes-q119-how-do-you-implement-multi-cluster-service-discovery-so-service-a-in-cluster-1-can-call-service-b-in-cluster-2-l3)
226. [Kubernetes Q120: What is a pause container and why is it in every pod [L2]](#scenario-226-kubernetes-q120-what-is-a-pause-container-and-why-is-it-in-every-pod-l2)
227. [Kubernetes Q121: What is imagePullPolicy Always vs IfNotPresent [L2]](#scenario-227-kubernetes-q121-what-is-imagepullpolicy-always-vs-ifnotpresent-l2)
228. [Kubernetes Q122: How do you configure resource requests and limits for init containers [L2]](#scenario-228-kubernetes-q122-how-do-you-configure-resource-requests-and-limits-for-init-containers-l2)
229. [Kubernetes Q123: What is a projected volume in Kubernetes [L3]](#scenario-229-kubernetes-q123-what-is-a-projected-volume-in-kubernetes-l3)
230. [Kubernetes Q124: How do you check what labels are on a node [L2]](#scenario-230-kubernetes-q124-how-do-you-check-what-labels-are-on-a-node-l2)
231. [Kubernetes Q125: What is the downward API in Kubernetes [L2]](#scenario-231-kubernetes-q125-what-is-the-downward-api-in-kubernetes-l2)
232. [Kubernetes Q126: How do you handle pod disruptions during Kubernetes version upgrades [L3]](#scenario-232-kubernetes-q126-how-do-you-handle-pod-disruptions-during-kubernetes-version-upgrades-l3)
233. [Kubernetes Q127: What is kubectl diff [L2]](#scenario-233-kubernetes-q127-what-is-kubectl-diff-l2)
234. [Kubernetes Q128: How do you enforce that all pods in a namespace must have resource limits [L2]](#scenario-234-kubernetes-q128-how-do-you-enforce-that-all-pods-in-a-namespace-must-have-resource-limits-l2)
235. [Kubernetes Q129: What is Vertical Pod Autoscaler (VPA) and when should you use it vs HPA [L3]](#scenario-235-kubernetes-q129-what-is-vertical-pod-autoscaler-vpa-and-when-should-you-use-it-vs-hpa-l3)
236. [Kubernetes Q130: How do you temporarily expose a service from a remote cluster to your local machine for debugging [L2]](#scenario-236-kubernetes-q130-how-do-you-temporarily-expose-a-service-from-a-remote-cluster-to-your-local-machine-for-debugging-l2)
237. [Kubernetes Q131: What is kubectl top and what does it need to work [L2]](#scenario-237-kubernetes-q131-what-is-kubectl-top-and-what-does-it-need-to-work-l2)
238. [Kubernetes Q132: How does Kubernetes handle pod security with the Pod Security Standards [L3]](#scenario-238-kubernetes-q132-how-does-kubernetes-handle-pod-security-with-the-pod-security-standards-l3)
239. [Kubernetes Q133: What is a Kubernetes lease [L2]](#scenario-239-kubernetes-q133-what-is-a-kubernetes-lease-l2)
240. [Kubernetes Q134: How do you get events for a specific namespace sorted by time [L2]](#scenario-240-kubernetes-q134-how-do-you-get-events-for-a-specific-namespace-sorted-by-time-l2)
241. [Kubernetes Q135: What is a Service Mesh and when is the complexity worth it [L3]](#scenario-241-kubernetes-q135-what-is-a-service-mesh-and-when-is-the-complexity-worth-it-l3)
242. [Kubernetes Q136: How do you forward all logs from a Kubernetes pod to Elasticsearch [L2]](#scenario-242-kubernetes-q136-how-do-you-forward-all-logs-from-a-kubernetes-pod-to-elasticsearch-l2)
243. [Kubernetes Q137: What is eBPF and how is it used in Kubernetes networking [L3]](#scenario-243-kubernetes-q137-what-is-ebpf-and-how-is-it-used-in-kubernetes-networking-l3)
244. [Kubernetes Q138: What happens when you delete a namespace that has resources in it [L2]](#scenario-244-kubernetes-q138-what-happens-when-you-delete-a-namespace-that-has-resources-in-it-l2)
245. [Kubernetes Q139: How do you run a pod on the control plane node [L2]](#scenario-245-kubernetes-q139-how-do-you-run-a-pod-on-the-control-plane-node-l2)
246. [Kubernetes Q140: Explain Kubernetes Network Policies default behavior and why it can be a security risk [L3]](#scenario-246-kubernetes-q140-explain-kubernetes-network-policies-default-behavior-and-why-it-can-be-a-security-risk-l3)
247. [Kubernetes Q141: What is a sidecar container pattern [L2]](#scenario-247-kubernetes-q141-what-is-a-sidecar-container-pattern-l2)
248. [Kubernetes Q142: How do you pass the pods own name to the app running inside it [L2]](#scenario-248-kubernetes-q142-how-do-you-pass-the-pods-own-name-to-the-app-running-inside-it-l2)
249. [Kubernetes Q143: What is Kubernetes Federation and is it still recommended [L3]](#scenario-249-kubernetes-q143-what-is-kubernetes-federation-and-is-it-still-recommended-l3)
250. [Kubernetes Q144: How do you create a self-signed TLS certificate for an Ingress [L2]](#scenario-250-kubernetes-q144-how-do-you-create-a-self-signed-tls-certificate-for-an-ingress-l2)
251. [Kubernetes Q145: What is an Admission Controller and how does Kubernetes use them [L3]](#scenario-251-kubernetes-q145-what-is-an-admission-controller-and-how-does-kubernetes-use-them-l3)
252. [Kubernetes Q146: How do you retrieve only the logs from a specific container in a pod that has multiple containers [L2]](#scenario-252-kubernetes-q146-how-do-you-retrieve-only-the-logs-from-a-specific-container-in-a-pod-that-has-multiple-containers-l2)
253. [Kubernetes Q147: What is kubectl apply --prune [L2]](#scenario-253-kubernetes-q147-what-is-kubectl-apply-prune-l2)
254. [Kubernetes Q148: How do you implement an egress gateway in a Kubernetes cluster [L3]](#scenario-254-kubernetes-q148-how-do-you-implement-an-egress-gateway-in-a-kubernetes-cluster-l3)
255. [Kubernetes Q149: What is the significance of the --dry-run=server flag vs --dry-run=client [L2]](#scenario-255-kubernetes-q149-what-is-the-significance-of-the-dry-run-server-flag-vs-dry-run-client-l2)
256. [Kubernetes Q150: How do you implement a global rate limiter for all requests to your services in Kubernetes [L3]](#scenario-256-kubernetes-q150-how-do-you-implement-a-global-rate-limiter-for-all-requests-to-your-services-in-kubernetes-l3)
257. [Multi-Cloud Docker Workload Architecture: Build Once, Deploy Portably](#scenario-257-multi-cloud-docker-workload-architecture-build-once-deploy-portably)
258. [Production Container Performance & Resource Monitoring Architecture](#scenario-258-production-container-performance-resource-monitoring-architecture)
259. [Live Coding Scenario: Writing an Optimized, Secure Multi-Stage Dockerfile](#scenario-259-live-coding-scenario-writing-an-optimized-secure-multi-stage-dockerfile)
260. [Integrating Jenkins with Docker, Kubernetes, and AWS (ECR/EKS) for Cloud-Native CI/CD](#scenario-260-integrating-jenkins-with-docker-kubernetes-and-aws-ecr-eks-for-cloud-native-ci-cd)
261. [Why Docker in Production: Eliminating Snowflake Environments & Configuration Drift](#scenario-261-why-docker-in-production-eliminating-snowflake-environments-configuration-drift)
262. [Container Image Security & AWS ECR Governance: Vulnerability Scanning, Signing & Lifecycle](#scenario-262-container-image-security-aws-ecr-governance-vulnerability-scanning-signing-lifecycle)

---

## 🛠️ Production Scenarios & First-Person Runbooks

<a id="scenario-1-ci-cd-pipeline-succeeds-but-new-version-isn-t-deployed-debugging"></a>
### 1. CI/CD Pipeline Succeeds but New Version Isn't Deployed — Debugging

**Level:** `Senior DevOps / SRE` | **Category:** `CI/CD` • `Pipelines & Delivery` | **Type:** `Pipeline Triage`

**Tags:** `CI/CD` `Docker` `Image Tagging` `GitOps` `Kubernetes`

> **Interview Question:**  
> *"Pipeline succeeds but the new version isn't deployed — how would you debug?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
When a CI/CD pipeline shows green but production is unchanged, the issue lies in artifact immutability, deployment trigger conditions, or GitOps reconciliation gaps.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Verify What is Actually Running in Production

Start by inspecting the live cluster/server before checking pipeline scripts:

- Run: `kubectl get deployment &lt;app&gt; -o jsonpath='{.spec.template.spec.containers[0].image}'`.
- Check the image tag and digest. Does it match the newly built Git commit SHA?
- Hit the application's version endpoint: `curl https://app.example.com/version`.

##### 2️⃣ The ':latest' Tag & imagePullPolicy Trap

The single most common root cause in container CI/CD:

- If the pipeline pushes `myapp:latest` and the Kubernetes Deployment manifest says `image: myapp:latest` with `imagePullPolicy: IfNotPresent`:
- Kubernetes checks if a tag named `latest` exists locally on the node. If yes, it **never pulls the new image from the registry!**
- Furthermore, Kubernetes detects no change in the Deployment manifest (the image string is still `myapp:latest`), so it triggers **zero rollout!**
- **Fix:** Always use immutable image tags based on Git SHA or semantic release (e.g. `myapp:sha-7f3a9b2`).

##### 3️⃣ Pipeline Step Conditions & Environment Mismatch

Audit pipeline execution steps:

- **Skipped Deploy Step:** Did the build/test job succeed, but the deploy job was skipped because of a condition like `if: github.ref == 'refs/heads/main'` when building a feature branch?
- **Target Environment Mismatch:** Did the pipeline deploy to Staging instead of Production due to environment variable configuration?
- **Manual Approval Gate:** Is the pipeline waiting on manual approval in GitHub Actions Environments / GitLab Protected Environments?

##### 4️⃣ GitOps Manifest Repo & Controller Audit

If using a separate manifest repository (ArgoCD / Flux):

- Did the CI pipeline successfully commit and push the updated image tag to the config repo? (Check git credentials and branch protection rules).
- Check ArgoCD sync status: Is the application in `OutOfSync` or `Sync Failed` state? Is auto-sync paused?
- Check for Kubernetes manifest validation failure (e.g. invalid YAML or unaccepted CPU limit).

#### 🎯 Key Architectural Takeaway
> Check the live running image tag first. Avoid mutable ':latest' tags that bypass k8s rollouts. Verify pipeline conditions, approval gates, and GitOps manifest commit chains.

#### ⏱️ 60-Second Elevator Pitch Summary

- Verify running container image: 'kubectl get deploy  -o jsonpath={..image}'.
- Check image tagging: Avoid ':latest' with 'imagePullPolicy: IfNotPresent' which ignores new image pushes.
- Audit CI logs: Ensure the deploy job actually executed and was not skipped by branch/tag conditions.
- Check GitOps repo: Verify CI successfully pushed new image tag commit to the manifest repository.
- Check ArgoCD/Flux: Inspect sync status, controller errors, or paused auto-sync.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-2-troubleshooting-imagepullbackoff-errimagepull-4-root-causes"></a>
### 2. Troubleshooting ImagePullBackOff & ErrImagePull — 4 Root Causes

**Level:** `Senior DevOps / SRE` | **Category:** `Kubernetes` • `Troubleshooting & Pod Lifecycle` | **Type:** `Core Troubleshooting`

**Tags:** `Kubernetes` `ImagePullBackOff` `Docker` `ECR` `ACR`

> **Interview Question:**  
> *"How do you troubleshoot ImagePullBackOff?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
ImagePullBackOff means kubelet tried to pull the container image from the registry, failed, and is backing off exponentially. My troubleshooting begins by running 'kubectl describe pod ' and reading the exact container runtime error in the Events.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Inspect Describe Events for the Exact Error String

Run `kubectl describe pod &lt;pod&gt; -n &lt;ns&gt;` and check the bottom Events section:

- `Error: ImagePullBackOff` is preceded by `Failed to pull image &lt;image-name&gt;: rpc error: code = NotFound / Unknown`.
- The exact error string immediately categorizes the failure into one of 4 root causes.

##### 2️⃣ Root Cause 1: Image Name or Tag Typo / Non-Existent Image

Error: `manifest unknown` or `repository does not exist`:

- Verify the repository URL, image name, and tag in `spec.containers[0].image`.
- Check if the CI/CD pipeline actually pushed the image to ECR/ACR/DockerHub, or if the build job failed before the push stage.
- Check for architecture mismatch (e.g. pushed ARM64 image while nodes are AMD64).

##### 3️⃣ Root Cause 2: Authentication & Missing imagePullSecrets

Error: `401 Unauthorized` or `403 Forbidden / Access Denied`:

- Private registries require Kubernetes credentials. Check if the Pod or its ServiceAccount references `imagePullSecrets`.
- Check secret existence: `kubectl get secret &lt;secret-name&gt; -o yaml`.
- In AWS EKS: Verify node IAM instance profile has `AmazonEC2ContainerRegistryReadOnly` or IRSA is configured.
- In Azure AKS: Verify AKS kubelet identity has `AcrPull` role assignment on the Azure Container Registry (ACR).

##### 4️⃣ Root Cause 3 & 4: Rate Limiting (429) & Network / Egress Blocks

Error: `toomanyrequests: You have reached your pull rate limit` or `i/o timeout`:

- **Docker Hub 429:** Free tier limits anonymous pulls to 100 per 6 hours. Solution: Mirror images to private ECR/ACR or add authenticated Docker Hub pull secret.
- **Network / DNS Timeout:** Worker nodes in private subnets cannot reach external registries if NAT Gateway is down, security group blocks outbound 443, or CoreDNS fails to resolve registry domain.
- **Quick Test from Node:** SSH into worker node or run a debug pod: `crictl pull &lt;image-name&gt;` to test pull directly.

#### 🎯 Key Architectural Takeaway
> Read the exact error in 'kubectl describe pod': 'manifest unknown' = image tag typo or unpushed image; '401/403' = missing imagePullSecret or IAM/AcrPull role; '429' = Docker Hub rate limit; 'i/o timeout' = NAT Gateway or egress firewall block.

#### ⏱️ 60-Second Elevator Pitch Summary

- Run 'kubectl describe pod ' and examine the Events message.
- Case 1: 'manifest unknown' -> Image tag typo or CI/CD failed to push image.
- Case 2: '401 Unauthorized' -> Missing imagePullSecret in pod spec or node lacks ECR/ACR IAM pull permissions.
- Case 3: '429 Too Many Requests' -> Docker Hub rate limit; switch to private registry mirror (ECR/ACR).
- Case 4: 'Connection timeout' -> Node in private subnet has no egress route to NAT Gateway or Security Group blocks 443 outbound.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-3-azure-kubernetes-service-aks-architecture-deployment-troubleshooting"></a>
### 3. Azure Kubernetes Service (AKS) — Architecture, Deployment & Troubleshooting

**Level:** `Senior DevOps / SRE` | **Category:** `Azure & Cloud` • `Managed Kubernetes` | **Type:** `AKS Mastery`

**Tags:** `Azure` `AKS` `Azure CNI` `Workload Identity` `Container Insights`

> **Interview Question:**  
> *"Have you worked with Azure Kubernetes Service (AKS)? How would you deploy, monitor, and troubleshoot applications on AKS?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
Yes, extensively. AKS provides a managed control plane while offloading worker node management into System and User node pools. Managing AKS effectively requires understanding Azure CNI networking, Workload Identity, and Azure Container Insights.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ AKS Architecture & Networking Fundamentals

Control plane and networking choices:

- **Architecture:** Free/Standard tier managed control plane (etcd, API server managed by Microsoft); customer pays only for Virtual Machine Scale Set (VMSS) worker nodes grouped into System (CoreDNS, Metrics Server) and User (microservices) node pools.
- **Azure CNI vs Kubenet:** **Kubenet** uses internal pod overlay subnets (saves VNet IPs). **Azure CNI** gives every pod a real, routable IP from the Azure VNet subnet (lower latency, Direct VNet integration, but requires careful VNet CIDR sizing to avoid IP exhaustion).

##### 2️⃣ Deploying Applications to AKS

Modern automated deployment workflow:

- CI pipeline builds image and pushes to Azure Container Registry (ACR).
- Authenticates to AKS using **Microsoft Entra Workload Identity** (OIDC federation—no long-lived service principal client secrets stored in CI).
- CD pipeline (or ArgoCD GitOps) renders Helm templates and applies manifests to AKS.

**Execution Flow:** `Git Push` ➔ `GitHub Actions / Azure Pipelines` ➔ `ACR Docker Build` ➔ `Workload Identity Auth` ➔ `ArgoCD / Helm Sync` ➔ `AKS Cluster`

##### 3️⃣ Monitoring & Troubleshooting in AKS

Diagnostic workflow when issues occur:

- **Monitoring:** Enable **Azure Monitor Container Insights** with Managed Prometheus and Grafana. Run KQL queries in Log Analytics: `ContainerInventory | where ContainerStatus == 'Failed'`.
- **Troubleshooting Pods:** Standard `kubectl describe pod` and `kubectl logs --previous`.
- **AKS Diagnose and Solve Problems:** Native Azure Portal blade that runs automated diagnostic checks on node readiness, subnet IP allocation, and API server throttles.
- **Node Issues:** Check VMSS instance health in Azure Portal or run `az aks check-acr` to verify network connectivity between AKS nodes and ACR.

#### 🎯 Key Architectural Takeaway
> AKS architecture relies on System vs User node pools, Azure CNI for routable VNet networking, and Entra Workload Identity for secretless IAM. Monitor via Azure Monitor Container Insights (Prometheus/Grafana) and troubleshoot using kubectl alongside the Azure 'Diagnose and Solve' blade.

#### ⏱️ 60-Second Elevator Pitch Summary

- Architecture: Microsoft-managed control plane + VMSS worker node pools (System pool for core add-ons, User pool for workloads).
- Networking: Azure CNI gives pods native VNet IPs; requires large subnets to prevent IP exhaustion.
- Security: Entra Workload Identity federates Kubernetes ServiceAccounts with Azure Managed Identities (zero stored keys).
- Deployment: Azure Pipelines / GitHub Actions -> build & scan image -> push to ACR -> deploy via Helm / ArgoCD.
- Troubleshooting: Use 'kubectl describe/logs' for pod issues; 'az aks check-acr' for registry connectivity; and the Azure Portal 'Diagnose and Solve Problems' blade for node and network health.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-4-ci-cd-q21-you-need-to-build-a-docker-image-in-a-gitlab-ci-pipeline-but-the-pipeline-runner-uses-docker-itself-how-do-you-solve-the-docker-in-docker-problem-l2"></a>
### 4. CI/CD Q21: You need to build a Docker image in a GitLab CI pipeline but the pipeline runner uses Docker itself How do you solve the Docker-in-Docker problem [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `CI/CD` • `Docker in CI/CD` | **Type:** `Production Scenario [L2]`

**Tags:** `CI/CD` `Docker in CI/CD` `L2` `DevOps` `Automation`

> **Interview Question:**  
> *"You need to build a Docker image in a GitLab CI pipeline but the pipeline runner uses Docker itself. How do you solve the "Docker-in-Docker" problem?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our delivery pipeline supporting multiple engineering squads, pipeline reliability was paramount. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Two approaches:

- Add `docker:dind` as a service in your GitLab CI job.
- Set `DOCKER_HOST: tcp://docker:2376`.
- Works but requires privileged mode. Security concern.

##### 2️⃣ Remediation & Permanent Safeguards

**Option 1: Docker-in-Docker (DinD)** **Option 2: Kaniko (recommended for security)** **Option 3: Buildah** — rootless container image build. Kaniko is the modern recommended approach for CI environments. ---

- Kaniko builds Docker images without Docker daemon.
- Runs as a normal container, no privileged mode needed.

```bash
build:
  image:
    name: gcr.io/kaniko-project/executor:latest
    entrypoint: [""]
  script:
    - /kaniko/executor --context . --destination my-registry/my-app:latest
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Add docker:dind as a service in your GitLab CI job..

#### ⏱️ 60-Second Elevator Pitch Summary

- Add docker:dind as a service in your GitLab CI job.
- Set DOCKER_HOST: tcp://docker:2376.
- Works but requires privileged mode. Security concern.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-5-ci-cd-q22-your-docker-images-are-huge-3gb-ci-pushes-take-forever-how-do-you-reduce-image-size-l2"></a>
### 5. CI/CD Q22: Your Docker images are huge (3GB) CI pushes take forever How do you reduce image size [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `CI/CD` • `Docker in CI/CD` | **Type:** `Production Scenario [L2]`

**Tags:** `CI/CD` `Docker in CI/CD` `L2` `DevOps` `Automation`

> **Interview Question:**  
> *"Your Docker images are huge (3GB). CI pushes take forever. How do you reduce image size?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When developers encounter this build or release bottleneck, my first goal is unblocking velocity safely. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Node image: 1GB. Node-alpine: 130MB. Huge difference.

- **Multi-stage builds** — build in one stage, copy only the artifact to a slim final stage:
- **Use slim/alpine base images** — `ubuntu` = 70MB, `alpine` = 5MB.
- **Clean up in the same layer** — `RUN apt-get update && apt-get install -y git && rm -rf /var/lib/apt/lists/*`.
- **`.dockerignore`** — exclude `node_modules`, `.git`, test files from build context.

##### 2️⃣ Remediation & Permanent Safeguards

---

- **Use `--no-install-recommends`** for apt installs.
- **Dive tool** — `dive ` shows which layers are large and what files are in them.

```bash
FROM node:18 AS builder
WORKDIR /app
COPY . .
RUN npm ci && npm run build

FROM node:18-alpine AS runtime
COPY --from=builder /app/dist ./dist
COPY --from=builder /app/node_modules ./node_modules
CMD ["node", "dist/index.js"]
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Multi-stage builds — build in one stage, copy only the artifact to a slim final stage:.

#### ⏱️ 60-Second Elevator Pitch Summary

- Multi-stage builds — build in one stage, copy only the artifact to a slim final stage:
- Use slim/alpine base images — ubuntu = 70MB, alpine = 5MB.
- Clean up in the same layer — RUN apt-get update && apt-get install -y git && rm -rf /var/lib/apt/...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-6-ci-cd-q23-youre-building-microservices-and-you-want-every-services-docker-image-to-be-uniquely-and-traceably-tagged-whats-your-tagging-strategy-l3"></a>
### 6. CI/CD Q23: Youre building microservices and you want every services Docker image to be uniquely and traceably tagged Whats your tagging strategy [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `CI/CD` • `Docker in CI/CD` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `CI/CD` `Docker in CI/CD` `L3` `DevOps` `Automation`

> **Interview Question:**  
> *"You're building microservices and you want every service's Docker image to be uniquely and traceably tagged. What's your tagging strategy?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"During a high-stakes release, we hit a similar deployment challenge and resolved it with automated safeguards. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Never use `latest` in production — it makes rollback and debugging impossible.

- **Git commit SHA** — `my-service:abc1234` — fully unique, traceable. `git rev-parse --short HEAD`.
- **Semantic version + SHA** — `my-service:1.4.2-abc1234` — human readable + traceable.
- **Branch + SHA for non-main branches** — `my-service:feature-login-abc1234` for testing.

##### 2️⃣ Remediation & Permanent Safeguards

Good strategies: Workflow: In Kubernetes, the deployment image tag is updated to the new SHA. ArgoCD/Flux detects the change and deploys. --- ## 🟣 Testing in CI ---

```bash
IMAGE_TAG=$CI_COMMIT_SHA  # GitLab
# or
IMAGE_TAG=$GITHUB_SHA     # GitHub Actions
docker build -t my-registry/my-service:$IMAGE_TAG .
docker push my-registry/my-service:$IMAGE_TAG
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Git commit SHA — my-service:abc1234 — fully unique, traceable. git rev-parse --short HEAD..

#### ⏱️ 60-Second Elevator Pitch Summary

- Git commit SHA — my-service:abc1234 — fully unique, traceable. git rev-parse --short HEAD.
- Semantic version + SHA — my-service:1.4.2-abc1234 — human readable + traceable.
- Branch + SHA for non-main branches — my-service:feature-login-abc1234 for testing.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-7-docker-q1-a-container-exits-immediately-after-starting-how-do-you-debug-it-l1"></a>
### 7. Docker Q1: A container exits immediately after starting How do you debug it [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Docker` • `Docker` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Docker` `Docker` `L1` `Containers` `Linux`

> **Interview Question:**  
> *"A container exits immediately after starting. How do you debug it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When containerizing our microservices stack, container lifecycle and resource management were critical. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`docker logs ` — read why it exited. Use `docker run -it  sh` to start interactively. Check the entrypoint/cmd. Common cause: the main process exits (e.g., a script returns 0), so the container stops. Containers live only as long as their PID 1 runs.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: docker logs  — read why it exited. Use docker run -it  sh to start interactively. Check the entrypoint/cmd. Common cause: the main.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: docker logs  — read why it exited. Use docker run -it  sh to start interactively. Check the ent
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-8-docker-q2-your-docker-build-fails-with-no-space-left-on-device-on-the-ci-server-what-do-you-do-l2"></a>
### 8. Docker Q2: Your Docker build fails with no space left on device on the CI server What do you do [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"Your Docker build fails with "no space left on device" on the CI server. What do you do?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In an interview, I explain how we diagnosed container runtime failures without guessing. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Clean up: `docker system prune -af` removes unused images, containers, volumes, build cache. `docker images | grep ''` finds dangling images. Set up automatic cleanup cron: `docker system prune -f --filter "until=24h"`. Long term: add more disk or use BuildKit with a cache limit.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Clean up: docker system prune -af removes unused images, containers, volumes, build cache. docker images | grep '' finds dangling .

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Clean up: docker system prune -af removes unused images, containers, volumes, build cache. dock
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-9-docker-q3-a-containerized-app-cant-connect-to-a-database-container-on-the-same-docker-host-whats-wrong-l2"></a>
### 9. Docker Q3: A containerized app cant connect to a database container on the same Docker host Whats wrong [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"A containerized app can't connect to a database container on the same Docker host. What's wrong?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"During an image optimization initiative across our services, we solved this exact problem. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

By default, containers are isolated. They need to be on the same Docker network. Create a network: `docker network create app-net`. Run both containers with `--network app-net`. Then use the container name as hostname. If using Docker Compose, all services in the same compose file are auto-networked.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: By default, containers are isolated. They need to be on the same Docker network. Create a network: docker network create app-net. .

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: By default, containers are isolated. They need to be on the same Docker network. Create a netwo
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-10-docker-q4-your-docker-image-is-2gb-how-do-you-reduce-it-l2"></a>
### 10. Docker Q4: Your Docker image is 2GB How do you reduce it [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"Your Docker image is 2GB. How do you reduce it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Container stability relies on clean signal handling (SIGTERM vs SIGKILL) and immutable image tagging. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Multi-stage build (build artifact in fat builder image, copy only artifact to slim runtime). Use alpine-based images. Clean up package manager cache in the same RUN layer. Remove build tools and test files. Use `.dockerignore`. Check with `docker history ` or `dive ` to find large layers.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Multi-stage build (build artifact in fat builder image, copy only artifact to slim runtime). Use alpine-based images. Clean up pac.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Multi-stage build (build artifact in fat builder image, copy only artifact to slim runtime). Us
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-11-docker-q5-how-do-containers-in-the-same-pod-kubernetes-communicate-vs-containers-in-different-pods-l2"></a>
### 11. Docker Q5: How do containers in the same pod (Kubernetes) communicate vs containers in different pods [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"How do containers in the same pod (Kubernetes) communicate vs containers in different pods?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When containerizing our microservices stack, container lifecycle and resource management were critical. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Same pod: share network namespace → communicate via `localhost`. Different pods: need a Kubernetes Service. Direct pod IP works but is ephemeral (changes on restart). Always use Service DNS names.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Same pod: share network namespace → communicate via localhost. Different pods: need a Kubernetes Service. Direct pod IP works but .

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Same pod: share network namespace → communicate via localhost. Different pods: need a Kubernete
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-12-docker-q6-you-need-to-run-a-docker-container-with-access-to-gpu-how-l3"></a>
### 12. Docker Q6: You need to run a Docker container with access to GPU How [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Docker` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Docker` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"You need to run a Docker container with access to GPU. How?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In an interview, I explain how we diagnosed container runtime failures without guessing. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Install NVIDIA Container Toolkit on the host. Run with `--gpus all` or `--gpus '"device=0"'`. In Docker Compose: `deploy: resources: reservations: devices:`. The container can then use CUDA APIs. Verify: `docker run --gpus all nvidia/cuda:11.0-base nvidia-smi`.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Install NVIDIA Container Toolkit on the host. Run with --gpus all or --gpus '"device=0"'. In Docker Compose: deploy: resources: re.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Install NVIDIA Container Toolkit on the host. Run with --gpus all or --gpus '"device=0"'. In Do
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-13-docker-q7-a-container-is-consuming-100-cpu-how-do-you-limit-it-without-restarting-l2"></a>
### 13. Docker Q7: A container is consuming 100% CPU How do you limit it without restarting [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"A container is consuming 100% CPU. How do you limit it without restarting?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"During an image optimization initiative across our services, we solved this exact problem. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`docker update --cpus="1.5" ` — limit to 1.5 CPU cores. Also `--memory="512m"` for memory limit. For Kubernetes, update the resource limits in the pod spec and trigger a rolling restart.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: docker update --cpus="1.5"  — limit to 1.5 CPU cores. Also --memory="512m" for memory limit. For Kubernetes, update the resource l.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: docker update --cpus="1.5"  — limit to 1.5 CPU cores. Also --memory="512m" for memory limit. Fo
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-14-docker-q8-explain-the-difference-between-copy-and-add-in-a-dockerfile-l2"></a>
### 14. Docker Q8: Explain the difference between COPY and ADD in a Dockerfile [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"Explain the difference between COPY and ADD in a Dockerfile."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Container stability relies on clean signal handling (SIGTERM vs SIGKILL) and immutable image tagging. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

COPY: copies files from build context to image. Simple and explicit. ADD: same as COPY but also supports URLs and auto-extracts tar archives. Prefer COPY — ADD's extra features make behavior less predictable. Use ADD only when you specifically need tar extraction.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: COPY: copies files from build context to image. Simple and explicit. ADD: same as COPY but also supports URLs and auto-extracts ta.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: COPY: copies files from build context to image. Simple and explicit. ADD: same as COPY but also
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-15-docker-q9-your-container-needs-to-run-as-a-non-root-user-for-security-how-do-you-set-this-up-l3"></a>
### 15. Docker Q9: Your container needs to run as a non-root user for security How do you set this up [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Docker` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Docker` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"Your container needs to run as a non-root user for security. How do you set this up?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When containerizing our microservices stack, container lifecycle and resource management were critical. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

The `USER` instruction sets the running user. Application files must be owned by this user. In Kubernetes, set `securityContext.runAsNonRoot: true` and `runAsUser: 1000`. Most base images now have a non-root user you can use (e.g., `node` user in Node.js images).

```bash
RUN groupadd -r appuser && useradd -r -g appuser appuser
COPY --chown=appuser:appuser . .
USER appuser
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: The USER instruction sets the running user. Application files must be owned by this user. In Kubernetes, set securityContext.runAs.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: dockerfile
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-16-docker-q10-what-is-the-difference-between-cmd-and-entrypoint-l2"></a>
### 16. Docker Q10: What is the difference between CMD and ENTRYPOINT [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"What is the difference between CMD and ENTRYPOINT?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In an interview, I explain how we diagnosed container runtime failures without guessing. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

ENTRYPOINT defines the main command that always runs. CMD provides default arguments. If ENTRYPOINT is `["nginx"]` and CMD is `["-g", "daemon off;"]`, running `docker run myimage -t` would execute `nginx -t` (CMD replaced by args). If only CMD: `docker run myimage bash` runs bash instead. Best practice: use ENTRYPOINT for the executable, CMD for default arguments.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: ENTRYPOINT defines the main command that always runs. CMD provides default arguments. If ENTRYPOINT is ["nginx"] and CMD is ["-g",.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: ENTRYPOINT defines the main command that always runs. CMD provides default arguments. If ENTRYP
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-17-docker-q11-how-do-you-share-data-between-the-host-and-a-container-l2"></a>
### 17. Docker Q11: How do you share data between the host and a container [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"How do you share data between the host and a container?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"During an image optimization initiative across our services, we solved this exact problem. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Bind mount: `docker run -v /host/path:/container/path`. Volume: `docker run -v myvolume:/container/path` (Docker manages storage location). Use bind mounts for development (live code changes). Use named volumes for production data (better performance, portable). Avoid bind mounts in production — ties container to specific host path.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Bind mount: docker run -v /host/path:/container/path. Volume: docker run -v myvolume:/container/path (Docker manages storage locat.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Bind mount: docker run -v /host/path:/container/path. Volume: docker run -v myvolume:/container
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-18-docker-q12-you-have-a-microservices-app-with-10-containers-how-do-you-manage-them-locally-l3"></a>
### 18. Docker Q12: You have a microservices app with 10 containers How do you manage them locally [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Docker` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Docker` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"You have a microservices app with 10 containers. How do you manage them locally?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Container stability relies on clean signal handling (SIGTERM vs SIGKILL) and immutable image tagging. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Docker Compose. Define all services in `docker-compose.yml`. `docker-compose up` starts everything. Auto-creates networks, manages startup order with `depends_on`, handles volume mounts. For production: Kubernetes. Compose is for local dev only.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Docker Compose. Define all services in docker-compose.yml. docker-compose up starts everything. Auto-creates networks, manages sta.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Docker Compose. Define all services in docker-compose.yml. docker-compose up starts everything.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-19-docker-q13-a-container-is-running-but-your-app-inside-it-crashed-docker-shows-the-container-as-up-why-l2"></a>
### 19. Docker Q13: A container is running but your app inside it crashed Docker shows the container as Up Why [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"A container is running but your app inside it crashed. Docker shows the container as "Up." Why?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When containerizing our microservices stack, container lifecycle and resource management were critical. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

The container's PID 1 (init process) is still running but the app process (a child) crashed. If using shell scripts as entrypoint, the shell is still alive even after the app it started dies. Fix: use `exec` in shell scripts to replace the shell with the app process: `exec node server.js`. Or use a proper init system in the container. Add a healthcheck to detect app failure.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: The container's PID 1 (init process) is still running but the app process (a child) crashed. If using shell scripts as entrypoint,.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: The container's PID 1 (init process) is still running but the app process (a child) crashed. If
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-20-docker-q14-how-do-you-view-resource-usage-cpu-memory-of-running-containers-l2"></a>
### 20. Docker Q14: How do you view resource usage (CPU memory) of running containers [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"How do you view resource usage (CPU, memory) of running containers?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In an interview, I explain how we diagnosed container runtime failures without guessing. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`docker stats` — live stream of CPU%, memory, network I/O, block I/O per container. `docker stats --no-stream` for a one-time snapshot. For historical metrics: use cAdvisor + Prometheus for container-level metrics, or cloud-native tools (CloudWatch Container Insights for ECS/EKS).

#### 🎯 Key Architectural Takeaway
> Pro-Tip: docker stats — live stream of CPU%, memory, network I/O, block I/O per container. docker stats --no-stream for a one-time snapshot.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: docker stats — live stream of CPU%, memory, network I/O, block I/O per container. docker stats
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-21-docker-q15-your-docker-compose-app-needs-to-wait-for-a-database-to-be-ready-before-starting-the-app-container-how-do-you-implement-this-l3"></a>
### 21. Docker Q15: Your Docker Compose app needs to wait for a database to be ready before starting the app container How do you implement this [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Docker` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Docker` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"Your Docker Compose app needs to wait for a database to be ready before starting the app container. How do you implement this?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"During an image optimization initiative across our services, we solved this exact problem. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

`depends_on` only waits for container start, not for the service inside to be ready.

- **wait-for-it.sh** — shell script that polls the DB port until it responds.
- **healthcheck + depends_on condition**:

##### 2️⃣ Remediation & Permanent Safeguards

Solutions: `service_healthy` waits for the healthcheck to pass before starting the app.

```bash
db:
  image: postgres
  healthcheck:
    test: ["CMD-SHELL", "pg_isready -U postgres"]
    interval: 5s

app:
  depends_on:
    db:
      condition: service_healthy
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: wait-for-it.sh — shell script that polls the DB port until it responds..

#### ⏱️ 60-Second Elevator Pitch Summary

- wait-for-it.sh — shell script that polls the DB port until it responds.
- healthcheck + depends_on condition:

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-22-docker-q16-what-is-docker-buildkit-and-why-is-it-better-than-the-classic-builder-l2"></a>
### 22. Docker Q16: What is Docker BuildKit and why is it better than the classic builder [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"What is Docker BuildKit and why is it better than the classic builder?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Container stability relies on clean signal handling (SIGTERM vs SIGKILL) and immutable image tagging. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

BuildKit is the modern Docker build backend. Benefits: parallel layer building (faster), better caching, secret mounts (pass secrets to build without storing in image), SSH mount for private repos, inline cache export, reduced image size. Enable: `DOCKER_BUILDKIT=1 docker build .` or set in Docker daemon config. Default in Docker 23+.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: BuildKit is the modern Docker build backend. Benefits: parallel layer building (faster), better caching, secret mounts (pass secre.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: BuildKit is the modern Docker build backend. Benefits: parallel layer building (faster), better
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-23-docker-q17-you-need-to-pass-a-github-token-to-npm-install-during-docker-build-without-it-ending-up-in-the-image-how-l3"></a>
### 23. Docker Q17: You need to pass a GitHub token to npm install during Docker build without it ending up in the image How [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Docker` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Docker` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"You need to pass a GitHub token to `npm install` during Docker build without it ending up in the image. How?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When containerizing our microservices stack, container lifecycle and resource management were critical. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

BuildKit secret mounts: Build: `docker build --secret id=github_token,src=~/.github_token .` The secret is available only during that RUN step and NOT stored in any layer.

```bash
RUN --mount=type=secret,id=github_token \
    export GITHUB_TOKEN=$(cat /run/secrets/github_token) && \
    npm install
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: BuildKit secret mounts:.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: BuildKit secret mounts:
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-24-docker-q18-what-is-the-difference-between-docker-stop-and-docker-kill-l2"></a>
### 24. Docker Q18: What is the difference between docker stop and docker kill [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"What is the difference between `docker stop` and `docker kill`?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In an interview, I explain how we diagnosed container runtime failures without guessing. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`docker stop` sends SIGTERM, waits 10 seconds (configurable), then SIGKILL. App can handle SIGTERM for graceful shutdown. `docker kill` sends SIGKILL immediately (or a specified signal). Use `stop` for normal shutdown. Use `kill` only when `stop` doesn't work.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: docker stop sends SIGTERM, waits 10 seconds (configurable), then SIGKILL. App can handle SIGTERM for graceful shutdown. docker kil.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: docker stop sends SIGTERM, waits 10 seconds (configurable), then SIGKILL. App can handle SIGTER
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-25-docker-q19-how-do-you-inspect-a-running-containers-environment-variables-and-configuration-l2"></a>
### 25. Docker Q19: How do you inspect a running containers environment variables and configuration [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"How do you inspect a running container's environment variables and configuration?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"During an image optimization initiative across our services, we solved this exact problem. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`docker inspect ` — full JSON config including environment variables, mounts, network, etc. `docker exec  env` — shows env vars from inside the container. `docker inspect --format='{{.Config.Env}}' ` for just env vars.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: docker inspect  — full JSON config including environment variables, mounts, network, etc. docker exec  env — shows env vars from i.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: docker inspect  — full JSON config including environment variables, mounts, network, etc. docke
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-26-docker-q20-explain-docker-networking-modes-l3"></a>
### 26. Docker Q20: Explain Docker networking modes [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Docker` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Docker` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"Explain Docker networking modes."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Container stability relies on clean signal handling (SIGTERM vs SIGKILL) and immutable image tagging. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

---

- `bridge` (default) — container gets its own IP on a virtual network. Containers talk via bridge or by name (user-defined networks).
- `host` — container shares the host's network namespace. No port mapping needed. Better performance. Less isolation.
- `none` — no networking. Completely isolated.

##### 2️⃣ Remediation & Permanent Safeguards

**Q21-Q60. Rapid-fire Docker Scenarios**

- `overlay` — for Docker Swarm. Connects containers across multiple hosts.
- `macvlan` — assigns a real MAC address from the host network. Container appears as a physical device on the network.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: bridge (default) — container gets its own IP on a virtual network. Containers talk via bridge or by name (user-defined networks)..

#### ⏱️ 60-Second Elevator Pitch Summary

- bridge (default) — container gets its own IP on a virtual network. Containers talk via bridge or ...
- host — container shares the host's network namespace. No port mapping needed. Better performance....
- none — no networking. Completely isolated.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-27-docker-q21-how-do-you-get-a-shell-inside-a-running-container-l1"></a>
### 27. Docker Q21: How do you get a shell inside a running container [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Docker` • `Docker` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Docker` `Docker` `L1` `Containers` `Linux`

> **Interview Question:**  
> *"How do you get a shell inside a running container?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When containerizing our microservices stack, container lifecycle and resource management were critical. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`docker exec -it  bash` or `sh` if bash isn't available.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: docker exec -it  bash or sh if bash isn't available..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: docker exec -it  bash or sh if bash isn't available.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-28-docker-q22-what-is-the-difference-between-a-docker-image-and-a-container-l1"></a>
### 28. Docker Q22: What is the difference between a Docker image and a container [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Docker` • `Docker` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Docker` `Docker` `L1` `Containers` `Linux`

> **Interview Question:**  
> *"What is the difference between a Docker image and a container?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In an interview, I explain how we diagnosed container runtime failures without guessing. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Image = read-only template (blueprint). Container = running instance of an image.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Image = read-only template (blueprint). Container = running instance of an image..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Image = read-only template (blueprint). Container = running instance of an image.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-29-docker-q23-how-do-you-copy-a-file-from-a-container-to-the-host-l2"></a>
### 29. Docker Q23: How do you copy a file from a container to the host [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"How do you copy a file from a container to the host?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"During an image optimization initiative across our services, we solved this exact problem. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`docker cp :/path/to/file /host/path`.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: docker cp :/path/to/file /host/path..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: docker cp :/path/to/file /host/path.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-30-docker-q24-your-container-image-build-is-failing-on-apt-get-update-whats-likely-wrong-l2"></a>
### 30. Docker Q24: Your container image build is failing on apt-get update Whats likely wrong [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"Your container image build is failing on `apt-get update`. What's likely wrong?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Container stability relies on clean signal handling (SIGTERM vs SIGKILL) and immutable image tagging. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Stale package lists or network issue. Add `--no-cache` to Docker build or restructure to always `apt-get update && apt-get install` in the same RUN command.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Stale package lists or network issue. Add --no-cache to Docker build or restructure to always apt-get update && apt-get install in.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Stale package lists or network issue. Add --no-cache to Docker build or restructure to always a
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-31-docker-q25-what-is-a-multi-stage-build-and-what-problem-does-it-solve-l2"></a>
### 31. Docker Q25: What is a multi-stage build and what problem does it solve [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"What is a multi-stage build and what problem does it solve?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When containerizing our microservices stack, container lifecycle and resource management were critical. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Multiple `FROM` statements in one Dockerfile. Build artifacts in a heavy build stage, copy only what's needed to a slim runtime stage. Final image contains no build tools, reducing size and attack surface.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Multiple FROM statements in one Dockerfile. Build artifacts in a heavy build stage, copy only what's needed to a slim runtime stag.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Multiple FROM statements in one Dockerfile. Build artifacts in a heavy build stage, copy only w
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-32-docker-q26-how-do-you-set-environment-variables-when-running-a-container-l2"></a>
### 32. Docker Q26: How do you set environment variables when running a container [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"How do you set environment variables when running a container?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In an interview, I explain how we diagnosed container runtime failures without guessing. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`docker run -e DB_HOST=localhost` or `docker run --env-file .env`. For Compose: `environment:` key or `env_file:` key.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: docker run -e DB_HOST=localhost or docker run --env-file .env. For Compose: environment: key or env_file: key..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: docker run -e DB_HOST=localhost or docker run --env-file .env. For Compose: environment: key or
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-33-docker-q27-a-container-writes-logs-to-a-file-instead-of-stdout-how-do-you-collect-these-logs-l2"></a>
### 33. Docker Q27: A container writes logs to a file instead of stdout How do you collect these logs [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"A container writes logs to a file instead of stdout. How do you collect these logs?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"During an image optimization initiative across our services, we solved this exact problem. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Mount a volume and use a log shipper sidecar to read and forward the file. Or configure the app to write to stdout. Containers should write to stdout/stderr — Docker captures these as container logs.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Mount a volume and use a log shipper sidecar to read and forward the file. Or configure the app to write to stdout. Containers sho.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Mount a volume and use a log shipper sidecar to read and forward the file. Or configure the app
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-34-docker-q28-how-do-you-scan-a-docker-image-for-vulnerabilities-before-pushing-to-a-registry-l3"></a>
### 34. Docker Q28: How do you scan a Docker image for vulnerabilities before pushing to a registry [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Docker` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Docker` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"How do you scan a Docker image for vulnerabilities before pushing to a registry?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Container stability relies on clean signal handling (SIGTERM vs SIGKILL) and immutable image tagging. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`trivy image ` — scans OS packages and app libraries for CVEs. Integrate in CI: fail the pipeline on HIGH/CRITICAL findings. Also: `docker scout cves` (Docker's built-in tool), `snyk container test`.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: trivy image  — scans OS packages and app libraries for CVEs. Integrate in CI: fail the pipeline on HIGH/CRITICAL findings. Also: d.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: trivy image  — scans OS packages and app libraries for CVEs. Integrate in CI: fail the pipeline
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-35-docker-q29-what-is-the-purpose-of-dockerignore-l2"></a>
### 35. Docker Q29: What is the purpose of dockerignore [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"What is the purpose of `.dockerignore`?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When containerizing our microservices stack, container lifecycle and resource management were critical. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Excludes files from the Docker build context. Smaller context = faster builds. Prevents accidentally copying secrets, `.git`, `node_modules` into the image.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Excludes files from the Docker build context. Smaller context = faster builds. Prevents accidentally copying secrets, .git, node_m.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Excludes files from the Docker build context. Smaller context = faster builds. Prevents acciden
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-36-docker-q30-how-do-you-implement-health-checks-in-docker-l3"></a>
### 36. Docker Q30: How do you implement health checks in Docker [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Docker` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Docker` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"How do you implement health checks in Docker?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In an interview, I explain how we diagnosed container runtime failures without guessing. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

In Dockerfile: `HEALTHCHECK --interval=30s --timeout=3s CMD curl -f http://localhost/health || exit 1`. Docker marks container as `healthy` or `unhealthy`. Compose and orchestrators use this for readiness.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: In Dockerfile: HEALTHCHECK --interval=30s --timeout=3s CMD curl -f http://localhost/health || exit 1. Docker marks container as he.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: In Dockerfile: HEALTHCHECK --interval=30s --timeout=3s CMD curl -f http://localhost/health || e
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-37-docker-q31-how-do-you-build-an-image-for-multiple-cpu-architectures-amd64-and-arm64-l2"></a>
### 37. Docker Q31: How do you build an image for multiple CPU architectures (AMD64 and ARM64) [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"How do you build an image for multiple CPU architectures (AMD64 and ARM64)?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"During an image optimization initiative across our services, we solved this exact problem. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Docker Buildx with QEMU emulation: `docker buildx build --platform linux/amd64,linux/arm64 -t myimage:latest --push .` Creates a multi-arch manifest. Users automatically get the right architecture.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Docker Buildx with QEMU emulation: docker buildx build --platform linux/amd64,linux/arm64 -t myimage:latest --push . Creates a mul.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Docker Buildx with QEMU emulation: docker buildx build --platform linux/amd64,linux/arm64 -t my
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-38-docker-q32-how-do-you-push-a-docker-image-to-a-private-registry-l2"></a>
### 38. Docker Q32: How do you push a Docker image to a private registry [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"How do you push a Docker image to a private registry?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Container stability relies on clean signal handling (SIGTERM vs SIGKILL) and immutable image tagging. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`docker login `. `docker tag myimage:latest /myimage:latest`. `docker push /myimage:latest`.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: docker login . docker tag myimage:latest /myimage:latest. docker push /myimage:latest..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: docker login . docker tag myimage:latest /myimage:latest. docker push /myimage:latest.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-39-docker-q33-what-does-expose-do-in-a-dockerfile-l2"></a>
### 39. Docker Q33: What does EXPOSE do in a Dockerfile [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"What does `EXPOSE` do in a Dockerfile?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When containerizing our microservices stack, container lifecycle and resource management were critical. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Documents which port the container listens on. Doesn't actually publish the port. To publish: `docker run -p 8080:3000 myimage`. `EXPOSE` is documentation, not security or networking configuration.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Documents which port the container listens on. Doesn't actually publish the port. To publish: docker run -p 8080:3000 myimage. EXP.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Documents which port the container listens on. Doesn't actually publish the port. To publish: d
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-40-docker-q34-how-do-you-run-docker-compose-in-production-l3"></a>
### 40. Docker Q34: How do you run Docker Compose in production [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Docker` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Docker` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"How do you run Docker Compose in production?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In an interview, I explain how we diagnosed container runtime failures without guessing. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Docker Compose is not recommended for production at scale. For production: Kubernetes (EKS/GKE/AKS), ECS, or Docker Swarm (simpler than K8s). Compose is for local development and simple single-host deployments.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Docker Compose is not recommended for production at scale. For production: Kubernetes (EKS/GKE/AKS), ECS, or Docker Swarm (simpler.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Docker Compose is not recommended for production at scale. For production: Kubernetes (EKS/GKE/
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-41-docker-q35-how-do-you-override-the-default-cmd-when-running-a-container-l2"></a>
### 41. Docker Q35: How do you override the default CMD when running a container [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"How do you override the default CMD when running a container?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"During an image optimization initiative across our services, we solved this exact problem. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Add arguments after the image name: `docker run myimage custom-command --flag`. This replaces CMD. To override ENTRYPOINT: `docker run --entrypoint /bin/bash myimage`.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Add arguments after the image name: docker run myimage custom-command --flag. This replaces CMD. To override ENTRYPOINT: docker ru.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Add arguments after the image name: docker run myimage custom-command --flag. This replaces CMD
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-42-docker-q36-what-is-an-init-container-not-kubernetes-why-might-you-use-init-in-docker-l2"></a>
### 42. Docker Q36: What is an init container (not Kubernetes) Why might you use --init in Docker [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"What is an `init` container (not Kubernetes)? Why might you use `--init` in Docker?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Container stability relies on clean signal handling (SIGTERM vs SIGKILL) and immutable image tagging. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`docker run --init` runs a tiny init process (tini) as PID 1. This properly handles zombie process reaping and signal forwarding. Without init, if PID 1 doesn't forward signals, `docker stop` becomes slow and unreliable.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: docker run --init runs a tiny init process (tini) as PID 1. This properly handles zombie process reaping and signal forwarding. Wi.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: docker run --init runs a tiny init process (tini) as PID 1. This properly handles zombie proces
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-43-docker-q37-how-do-you-debug-a-container-that-crashes-before-you-can-exec-into-it-l3"></a>
### 43. Docker Q37: How do you debug a container that crashes before you can exec into it [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Docker` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Docker` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"How do you debug a container that crashes before you can exec into it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When containerizing our microservices stack, container lifecycle and resource management were critical. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Override the entrypoint to sleep: `docker run --entrypoint sleep myimage 300`. Then exec in and investigate. Or: `docker run --entrypoint /bin/sh -it myimage` to get a shell without running the main app.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Override the entrypoint to sleep: docker run --entrypoint sleep myimage 300. Then exec in and investigate. Or: docker run --entryp.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Override the entrypoint to sleep: docker run --entrypoint sleep myimage 300. Then exec in and i
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-44-docker-q38-what-is-image-layer-caching-and-why-does-layer-order-matter-l2"></a>
### 44. Docker Q38: What is image layer caching and why does layer ORDER matter [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"What is image layer caching and why does layer ORDER matter?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In an interview, I explain how we diagnosed container runtime failures without guessing. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Docker reuses unchanged layers from cache. Layers that change early in the Dockerfile invalidate all subsequent layers. Put slow-changing layers (base image, dependencies) first. Put fast-changing layers (app code) last.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Docker reuses unchanged layers from cache. Layers that change early in the Dockerfile invalidate all subsequent layers. Put slow-c.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Docker reuses unchanged layers from cache. Layers that change early in the Dockerfile invalidat
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-45-docker-q39-how-do-you-see-which-processes-are-running-inside-a-container-l2"></a>
### 45. Docker Q39: How do you see which processes are running inside a container [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"How do you see which processes are running inside a container?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"During an image optimization initiative across our services, we solved this exact problem. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`docker top ` — shows running processes. `docker exec  ps aux` for more detail.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: docker top  — shows running processes. docker exec  ps aux for more detail..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: docker top  — shows running processes. docker exec  ps aux for more detail.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-46-docker-q40-explain-docker-content-trust-dct-and-why-it-matters-l3"></a>
### 46. Docker Q40: Explain Docker content trust (DCT) and why it matters [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Docker` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Docker` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"Explain Docker content trust (DCT) and why it matters."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Container stability relies on clean signal handling (SIGTERM vs SIGKILL) and immutable image tagging. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

DCT allows image publishers to sign images and consumers to verify signatures. `DOCKER_CONTENT_TRUST=1` enforces that only signed images can be pulled/run. Prevents running tampered images. Important for supply chain security.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: DCT allows image publishers to sign images and consumers to verify signatures. DOCKER_CONTENT_TRUST=1 enforces that only signed im.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: DCT allows image publishers to sign images and consumers to verify signatures. DOCKER_CONTENT_T
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-47-docker-q41-what-is-a-dangling-image-in-docker-l2"></a>
### 47. Docker Q41: What is a dangling image in Docker [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"What is a "dangling image" in Docker?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When containerizing our microservices stack, container lifecycle and resource management were critical. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

An untagged image (shows as `:`). Created when you build a new image with the same tag — the old layers lose their tag. Clean up: `docker image prune`.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: An untagged image (shows as :). Created when you build a new image with the same tag — the old layers lose their tag. Clean up: do.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: An untagged image (shows as :). Created when you build a new image with the same tag — the old
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-48-docker-q42-how-do-you-set-resource-limits-for-a-docker-compose-service-l2"></a>
### 48. Docker Q42: How do you set resource limits for a Docker Compose service [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"How do you set resource limits for a Docker Compose service?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In an interview, I explain how we diagnosed container runtime failures without guessing. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Under `deploy.resources.limits`: `cpus: '0.5'` and `memory: 512M`. Note: `deploy` key is only respected by Swarm mode; for regular Compose use `mem_limit` and `cpus` at the service level.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Under deploy.resources.limits: cpus: '0.5' and memory: 512M. Note: deploy key is only respected by Swarm mode; for regular Compose.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Under deploy.resources.limits: cpus: '0.5' and memory: 512M. Note: deploy key is only respected
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-49-docker-q43-how-does-container-networking-work-at-the-linux-kernel-level-l3"></a>
### 49. Docker Q43: How does container networking work at the Linux kernel level [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Docker` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Docker` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"How does container networking work at the Linux kernel level?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"During an image optimization initiative across our services, we solved this exact problem. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Each container gets a network namespace. A virtual ethernet pair (veth) connects the container's namespace to a Linux bridge (docker0). iptables rules handle NAT for outbound traffic and port mapping for inbound. The bridge routes traffic between containers on the same network.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Each container gets a network namespace. A virtual ethernet pair (veth) connects the container's namespace to a Linux bridge (dock.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Each container gets a network namespace. A virtual ethernet pair (veth) connects the container'
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-50-docker-q44-how-do-you-rebuild-only-a-specific-service-in-docker-compose-l2"></a>
### 50. Docker Q44: How do you rebuild only a specific service in Docker Compose [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"How do you rebuild only a specific service in Docker Compose?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Container stability relies on clean signal handling (SIGTERM vs SIGKILL) and immutable image tagging. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`docker-compose build ` then `docker-compose up -d `. Compose won't rebuild services that haven't changed unless you add `--build` flag.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: docker-compose build  then docker-compose up -d . Compose won't rebuild services that haven't changed unless you add --build flag..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: docker-compose build  then docker-compose up -d . Compose won't rebuild services that haven't c
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-51-docker-q45-what-is-the-difference-between-docker-compose-up-and-docker-compose-run-l2"></a>
### 51. Docker Q45: What is the difference between docker-compose up and docker-compose run [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"What is the difference between `docker-compose up` and `docker-compose run`?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When containerizing our microservices stack, container lifecycle and resource management were critical. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`up` starts all services defined in the compose file as long-running services. `run` runs a one-off command in a service container: `docker-compose run app pytest`. Useful for running migrations, tests, one-time scripts.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: up starts all services defined in the compose file as long-running services. run runs a one-off command in a service container: do.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: up starts all services defined in the compose file as long-running services. run runs a one-off
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-52-docker-q46-you-need-to-run-a-container-with-access-to-the-hosts-unix-socket-eg-docker-socket-what-are-the-security-implications-l3"></a>
### 52. Docker Q46: You need to run a container with access to the hosts Unix socket (eg Docker socket) What are the security implications [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Docker` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Docker` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"You need to run a container with access to the host's Unix socket (e.g., Docker socket). What are the security implications?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In an interview, I explain how we diagnosed container runtime failures without guessing. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Mounting the Docker socket (`/var/run/docker.sock`) gives the container full control over the Docker daemon — effectively root on the host. Extremely dangerous. Alternative: use Docker socket proxy (Tecnativa) that limits which API calls the container can make. Never mount Docker socket in production unless absolutely necessary.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Mounting the Docker socket (/var/run/docker.sock) gives the container full control over the Docker daemon — effectively root on th.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Mounting the Docker socket (/var/run/docker.sock) gives the container full control over the Doc
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-53-docker-q47-how-do-you-roll-back-to-a-previous-docker-image-version-in-kubernetes-l2"></a>
### 53. Docker Q47: How do you roll back to a previous Docker image version in Kubernetes [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"How do you roll back to a previous Docker image version in Kubernetes?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"During an image optimization initiative across our services, we solved this exact problem. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Update the image tag in the deployment to the previous version's tag. `kubectl set image deployment/app container=registry/app:v1.2.3`. Or `kubectl rollout undo deployment/app` if using Deployment rollout history.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Update the image tag in the deployment to the previous version's tag. kubectl set image deployment/app container=registry/app:v1.2.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Update the image tag in the deployment to the previous version's tag. kubectl set image deploym
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-54-docker-q48-what-is-docker-swarm-and-how-does-it-compare-to-kubernetes-l2"></a>
### 54. Docker Q48: What is Docker Swarm and how does it compare to Kubernetes [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"What is Docker Swarm and how does it compare to Kubernetes?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Container stability relies on clean signal handling (SIGTERM vs SIGKILL) and immutable image tagging. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Docker Swarm is Docker's built-in orchestration. Simpler to set up and use than Kubernetes. Less features (no Ingress, limited scheduling, smaller ecosystem). Good for: simple orchestration, small teams, single-cloud. Most production workloads have moved to Kubernetes.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Docker Swarm is Docker's built-in orchestration. Simpler to set up and use than Kubernetes. Less features (no Ingress, limited sch.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Docker Swarm is Docker's built-in orchestration. Simpler to set up and use than Kubernetes. Les
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-55-docker-q49-how-do-you-optimize-docker-builds-in-a-monorepo-where-multiple-services-share-code-l3"></a>
### 55. Docker Q49: How do you optimize Docker builds in a monorepo where multiple services share code [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Docker` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Docker` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"How do you optimize Docker builds in a monorepo where multiple services share code?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When containerizing our microservices stack, container lifecycle and resource management were critical. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use BuildKit's `--build-context` to pass multiple directories as build context. Use cache mounts for shared dependencies. Or extract shared code to a private package registry (npm, PyPI). Build parent images with shared deps, extend in child service Dockerfiles: `FROM shared-base:latest`.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use BuildKit's --build-context to pass multiple directories as build context. Use cache mounts for shared dependencies. Or extract.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use BuildKit's --build-context to pass multiple directories as build context. Use cache mounts
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-56-docker-q50-how-do-you-make-sure-containers-restart-on-host-reboot-l2"></a>
### 56. Docker Q50: How do you make sure containers restart on host reboot [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"How do you make sure containers restart on host reboot?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In an interview, I explain how we diagnosed container runtime failures without guessing. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`docker run --restart=unless-stopped` — restarts always except when manually stopped. Or `--restart=always`. Docker Compose: `restart: unless-stopped` in the service definition.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: docker run --restart=unless-stopped — restarts always except when manually stopped. Or --restart=always. Docker Compose: restart: .

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: docker run --restart=unless-stopped — restarts always except when manually stopped. Or --restar
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-57-docker-q51-what-is-the-purpose-of-docker-commit-l2"></a>
### 57. Docker Q51: What is the purpose of docker commit [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"What is the purpose of `docker commit`?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"During an image optimization initiative across our services, we solved this exact problem. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Creates a new image from a running container's current state. Rarely used in production (not reproducible). Use it for: quick debugging snapshots. Never for production images — always use Dockerfiles for reproducibility.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Creates a new image from a running container's current state. Rarely used in production (not reproducible). Use it for: quick debu.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Creates a new image from a running container's current state. Rarely used in production (not re
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-58-docker-q52-how-do-you-pass-build-arguments-not-environment-variables-to-a-docker-build-l2"></a>
### 58. Docker Q52: How do you pass build arguments (not environment variables) to a Docker build [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"How do you pass build arguments (not environment variables) to a Docker build?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Container stability relies on clean signal handling (SIGTERM vs SIGKILL) and immutable image tagging. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`ARG VERSION=latest` in Dockerfile. Build: `docker build --build-arg VERSION=1.2.3 .`. ARG values are available only at build time, not at runtime (use ENV for runtime). Don't pass secrets via ARG — they appear in image history.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: ARG VERSION=latest in Dockerfile. Build: docker build --build-arg VERSION=1.2.3 .. ARG values are available only at build time, no.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: ARG VERSION=latest in Dockerfile. Build: docker build --build-arg VERSION=1.2.3 .. ARG values a
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-59-docker-q53-how-do-you-implement-a-docker-image-garbage-collection-policy-in-a-registry-l3"></a>
### 59. Docker Q53: How do you implement a Docker image garbage collection policy in a registry [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Docker` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Docker` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"How do you implement a Docker image garbage collection policy in a registry?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When containerizing our microservices stack, container lifecycle and resource management were critical. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

ECR lifecycle policies: keep only last N images, delete untagged images after X days. `aws ecr put-lifecycle-policy --lifecycle-policy-text file://policy.json`. For Docker Hub: use retention policies. This prevents registry storage costs from growing indefinitely.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: ECR lifecycle policies: keep only last N images, delete untagged images after X days. aws ecr put-lifecycle-policy --lifecycle-pol.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: ECR lifecycle policies: keep only last N images, delete untagged images after X days. aws ecr p
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-60-docker-q54-what-does-docker-save-and-docker-load-do-l2"></a>
### 60. Docker Q54: What does docker save and docker load do [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"What does `docker save` and `docker load` do?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In an interview, I explain how we diagnosed container runtime failures without guessing. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`docker save myimage > image.tar` — exports image to a tar file. `docker load < image.tar` — imports it. Use for air-gapped environments (no internet, can't pull from registry). Also for shipping specific image versions.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: docker save myimage > image.tar — exports image to a tar file. docker load  — imports it. Use for air-gapped environments (no inte.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: docker save myimage > image.tar — exports image to a tar file. docker load < image.tar — import
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-61-docker-q55-how-do-you-ensure-your-containers-run-with-the-minimum-required-linux-capabilities-l3"></a>
### 61. Docker Q55: How do you ensure your containers run with the minimum required Linux capabilities [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Docker` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Docker` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"How do you ensure your containers run with the minimum required Linux capabilities?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"During an image optimization initiative across our services, we solved this exact problem. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Drop all capabilities, add only needed ones: In K8s: `securityContext.capabilities.drop: ["ALL"]`, then `add: ["NET_BIND_SERVICE"]`. Running with reduced capabilities limits what a compromised container can do.

```bash
docker run --cap-drop ALL --cap-add NET_BIND_SERVICE myimage
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Drop all capabilities, add only needed ones:.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Drop all capabilities, add only needed ones:
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-62-docker-q56-how-do-you-view-the-docker-build-history-layers-of-an-image-l2"></a>
### 62. Docker Q56: How do you view the Docker build history/layers of an image [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"How do you view the Docker build history/layers of an image?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Container stability relies on clean signal handling (SIGTERM vs SIGKILL) and immutable image tagging. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`docker history ` — shows each layer, its size, and the command that created it. Use `--no-trunc` to see full commands. `dive ` for interactive layer explorer.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: docker history  — shows each layer, its size, and the command that created it. Use --no-trunc to see full commands. dive  for inte.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: docker history  — shows each layer, its size, and the command that created it. Use --no-trunc t
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-63-docker-q57-what-is-the-difference-between-volume-instruction-and-runtime-volume-mount-l2"></a>
### 63. Docker Q57: What is the difference between VOLUME instruction and runtime volume mount [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"What is the difference between `VOLUME` instruction and runtime volume mount?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When containerizing our microservices stack, container lifecycle and resource management were critical. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`VOLUME /data` in Dockerfile tells Docker this path should be a volume. Docker auto-creates an anonymous volume at that path if none is provided. Runtime `-v` explicitly mounts a named volume or bind mount. VOLUME instructions ensure data isn't stored in the container layer even if no explicit mount is given.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: VOLUME /data in Dockerfile tells Docker this path should be a volume. Docker auto-creates an anonymous volume at that path if none.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: VOLUME /data in Dockerfile tells Docker this path should be a volume. Docker auto-creates an an
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-64-docker-q58-how-do-you-run-integration-tests-in-ci-that-require-real-external-services-redis-kafka-using-docker-l3"></a>
### 64. Docker Q58: How do you run integration tests in CI that require real external services (Redis Kafka) using Docker [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Docker` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Docker` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"How do you run integration tests in CI that require real external services (Redis, Kafka) using Docker?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In an interview, I explain how we diagnosed container runtime failures without guessing. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Docker Compose in CI (all services started via compose). Or CI service containers (GitHub Actions services, GitLab CI services). Or testcontainers — a library that programmatically starts Docker containers from test code. Tests spin up the exact services they need, test runs, containers are destroyed.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Docker Compose in CI (all services started via compose). Or CI service containers (GitHub Actions services, GitLab CI services). O.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Docker Compose in CI (all services started via compose). Or CI service containers (GitHub Actio
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-65-docker-q59-how-do-you-debug-network-connectivity-between-two-containers-l2"></a>
### 65. Docker Q59: How do you debug network connectivity between two containers [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"How do you debug network connectivity between two containers?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"During an image optimization initiative across our services, we solved this exact problem. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`docker network inspect ` — see which containers are on the network. From one container: `ping ` (if on same user-defined network). `nslookup ` to verify DNS. `curl http://:` to test HTTP.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: docker network inspect  — see which containers are on the network. From one container: ping  (if on same user-defined network). ns.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: docker network inspect  — see which containers are on the network. From one container: ping  (i
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-66-docker-q60-explain-the-security-implications-of-running-containers-in-privileged-mode-and-when-its-acceptable-l3"></a>
### 66. Docker Q60: Explain the security implications of running containers in privileged mode and when its acceptable [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Docker` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Docker` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"Explain the security implications of running containers in privileged mode and when it's acceptable."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Container stability relies on clean signal handling (SIGTERM vs SIGKILL) and immutable image tagging. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Privileged containers can access all devices, modify kernel parameters, and escape the container namespace. They have near-root access to the host. Acceptable only for: kernel-level tools, CNI plugins, certain monitoring agents, Docker-in-Docker (use Kaniko instead). In production: block with PSA/OPA. Log privileged container creation as a security event. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Privileged containers can access all devices, modify kernel parameters, and escape the container namespace. They have near-root ac.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Privileged containers can access all devices, modify kernel parameters, and escape the containe
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-67-docker-q61-a-junior-developer-complains-that-every-time-they-edit-a-file-on-their-host-machine-the-changes-dont-physically-appear-inside-the-docker-container-despite-having-a-bind-mount-configured-what-is-the-most-likely-culprit-l2"></a>
### 67. Docker Q61: A junior developer complains that every time they edit a file on their host machine the changes dont physically appear inside the Docker container despite having a bind mount configured What is the most likely culprit [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"A junior developer complains that every time they edit a file on their host machine, the changes don't physically appear inside the Docker container despite having a bind mount configured. What is the most likely culprit?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When containerizing our microservices stack, container lifecycle and resource management were critical. The interviewer is testing: Inode changing from text editors, bind mount mechanics.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

If they bind-mounted a *single file* (e.g., `-v /path/to/app.py:/app/app.py`) instead of a directory, the issue is how modern text editors (like Vim or some IDEs) save files. When you save a file in Vim, it often creates a temporary file, deletes the original file, and renames the temp file to the original name. This completely changes the file's **inode**. Docker bind-mounts are explicitly tied to the inode present at the exact moment the container started. Because the host editor created a new inode, the container continues looking at the old (now deleted/hidden) inode and misses the updates. *Fix:* Bind-mount the *entire directory* (e.g., `-v /path/to:/app`) rather than the individual file. The directory's inode doesn't change when files inside it are updated. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: If they bind-mounted a *single file* (e.g., -v /path/to/app.py:/app/app.py) instead of a directory, the issue is how modern text e.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: If they bind-mounted a single file (e.g., -v /path/to/app.py:/app/app.py) instead of a director
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-68-docker-q62-you-set-up-a-strict-ufw-uncomplicated-firewall-on-your-ubuntu-server-to-block-all-incoming-traffic-to-port-8080-you-then-run-a-docker-container-docker-run-p-808080-myapp-miraculously-a-hacker-easily-accesses-your-app-on-port-8080-from-the-internet-why-did-the-firewall-fail-l3"></a>
### 68. Docker Q62: You set up a strict UFW (Uncomplicated Firewall) on your Ubuntu server to block all incoming traffic to port 8080 You then run a Docker container docker run -p 808080 myapp Miraculously a hacker easily accesses your app on port 8080 from the internet Why did the firewall fail [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Docker` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Docker` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"You set up a strict UFW (Uncomplicated Firewall) on your Ubuntu server to block all incoming traffic to port 8080. You then run a Docker container `docker run -p 8080:80 myapp`. Miraculously, a hacker easily accesses your app on port 8080 from the internet. Why did the firewall fail?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In an interview, I explain how we diagnosed container runtime failures without guessing. The interviewer is testing: Docker networking vs. Host iptables/UFW integration.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Docker bypasses UFW by design. When Docker starts, it actively manipulates the Linux `iptables` directly by inserting its own rules at the absolute top of the `PREROUTING` chain in the `nat` table (in a chain called `DOCKER`). Because UFW operates primarily in the `INPUT` chain, the traffic hitting port 8080 is intercepted by Docker's `PREROUTING` rule *before* UFW ever sees it, and routed directly into the container. *Fix:* Never rely on host OS firewalls to protect exposed Docker ports. You must either not publish the port `8080` to the internet (bind it to localhost `-p 127.0.0.1:8080:80`), or modify the Docker daemon configuration to set `"iptables": false` (which breaks many standard Docker networking features). ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Docker bypasses UFW by design..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Docker bypasses UFW by design.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-69-docker-q63-a-container-exits-with-code-137-what-does-this-specific-code-universally-mean-in-the-docker-ecosystem-and-where-should-you-look-next-l1"></a>
### 69. Docker Q63: A container exits with code 137 What does this specific code universally mean in the Docker ecosystem and where should you look next [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Docker` • `Docker` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Docker` `Docker` `L1` `Containers` `Linux`

> **Interview Question:**  
> *"A container exits with code `137`. What does this specific code universally mean in the Docker ecosystem, and where should you look next?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"During an image optimization initiative across our services, we solved this exact problem. The interviewer is testing: Exit code evaluation, OOM killer.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Exit code `137` specifically means the container received a `SIGKILL` (signal 9) and was abruptly terminated ($128 + 9 = 137$). In 90% of Docker/Kubernetes scenarios, this means the container was violently killed by the **OOM (Out Of Memory) Killer** because it exceeded its allocated memory limits. *Next Steps:* I would immediately run `docker inspect ` and check the `State.OOMKilled` boolean flag to confirm. Then, I would review application memory profiling and potentially increase the `-m` (memory limit) on the container runtime. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Exit code 137 specifically means the container received a SIGKILL (signal 9) and was abruptly terminated ($128 + 9 = 137$)..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Exit code 137 specifically means the container received a SIGKILL (signal 9) and was abruptly t
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-70-docker-q64-you-are-tasked-with-debugging-a-critically-failing-production-container-however-the-container-is-built-distroless-it-has-absolutely-no-shell-no-bash-no-ls-no-curl-docker-exec-fails-with-executable-file-not-found-in-path-how-do-you-run-debugging-tools-against-this-container-l3"></a>
### 70. Docker Q64: You are tasked with debugging a critically failing production container However the container is built Distroless (it has absolutely no shell no bash no ls no curl) docker exec fails with executable file not found in $PATH How do you run debugging tools against this container [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Docker` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Docker` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"You are tasked with debugging a critically failing production container. However, the container is built "Distroless" (it has absolutely no shell, no `bash`, no `ls`, no `curl`). `docker exec` fails with "executable file not found in $PATH". How do you run debugging tools against this container?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Container stability relies on clean signal handling (SIGTERM vs SIGKILL) and immutable image tagging. The interviewer is testing: Namespaces, `nsenter`, ephemeral debug containers.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

You cannot `exec` a shell if the shell binary literally doesn't exist inside the container. You must inject tools from the outside using Linux namespaces.

- **Find the PID:** Run `docker inspect --format '{{.State.Pid}}' `. (e.g., PID 1234).
- **Use nsenter:** As a root user on the host, use `nsenter` to run a host shell *inside* the network, mount, and PID namespaces of the container:
- **Alternative (K8s):** Use Ephemeral Containers (`kubectl debug`), which attach a sidecar (like an Alpine/Ubuntu image) sharing the exact same network namespace.

##### 2️⃣ Remediation & Permanent Safeguards

`sudo nsenter -t 1234 -n -p -m /bin/bash` This gives you full host tools running under the exact perspective of the distroless container. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Find the PID: Run docker inspect --format '{{.State.Pid}}' . (e.g., PID 1234)..

#### ⏱️ 60-Second Elevator Pitch Summary

- Find the PID: Run docker inspect --format '{{.State.Pid}}' . (e.g., PID 1234).
- Use nsenter: As a root user on the host, use nsenter to run a host shell *inside* the network, mo...
- Alternative (K8s): Use Ephemeral Containers (kubectl debug), which attach a sidecar (like an Alpi...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-71-docker-q65-a-python-data-science-container-parsing-massive-multi-gigabyte-pandas-dataframes-suddenly-crashes-randomly-the-code-is-flawless-the-server-has-128gb-of-ram-and-oomkilled-is-false-you-notice-the-crash-happens-specifically-when-multiprocessing-writes-heavily-what-hidden-docker-limit-is-causing-this-l2"></a>
### 71. Docker Q65: A Python data science container parsing massive multi-gigabyte pandas dataframes suddenly crashes randomly The code is flawless the server has 128GB of RAM and OOMKilled is false You notice the crash happens specifically when multiprocessing writes heavily What hidden Docker limit is causing this [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"A Python data science container parsing massive multi-gigabyte pandas dataframes suddenly crashes randomly. The code is flawless, the server has 128GB of RAM, and OOMKilled is false. You notice the crash happens specifically when multiprocessing writes heavily. What hidden Docker limit is causing this?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When containerizing our microservices stack, container lifecycle and resource management were critical. The interviewer is testing: Shared memory (`shm_size`) limits.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

The container is exhausting its **Shared Memory (`/dev/shm`) limit**. By default, Docker allocates an incredibly tiny `64MB` to `/dev/shm` for every container. Python multiprocessing, Postgres databases, and tools like Google Chrome Heavily utilize shared memory to pass data quickly between worker processes. When they try to write a 1GB dataframe into the 64MB shared memory space, they immediately crash with obscure "Bus error" or memory exceptions. *Fix:* Run the container with an explicitly increased shared memory limit: `docker run --shm-size="2g" myapp`. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: The container is exhausting its Shared Memory (/dev/shm) limit..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: The container is exhausting its Shared Memory (/dev/shm) limit.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-72-docker-q66-a-developer-submits-a-dockerfile-that-copies-a-5gb-file-runs-a-command-to-compress-it-to-100mb-and-then-runs-rm-to-delete-the-original-5gb-file-in-the-next-step-why-does-the-final-docker-image-still-weigh-over-5gb-l1"></a>
### 72. Docker Q66: A developer submits a Dockerfile that copies a 5GB file runs a command to compress it to 100MB and then runs rm to delete the original 5GB file in the next step Why does the final Docker image still weigh over 5GB [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Docker` • `Docker` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Docker` `Docker` `L1` `Containers` `Linux`

> **Interview Question:**  
> *"A developer submits a Dockerfile that copies a 5GB file, runs a command to compress it to 100MB, and then runs `rm` to delete the original 5GB file in the next step. Why does the final Docker image still weigh over 5GB?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In an interview, I explain how we diagnosed container runtime failures without guessing. The interviewer is testing: Intersecting image layers natively, Copy-on-Write storage.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Dockerfile instructions like `COPY`, `RUN`, and `ADD` create immutable, read-only layers. When the developer copied the 5GB file in Layer 1, it was permanently baked into the image history. When they deleted it in Layer 3 using a subsequent `RUN rm` command, Docker merely created a new layer with a "whiteout" marker hiding the file. The original 5GB file still exists underneath and is physically downloaded by anyone pulling the image. *Fix:* Operations that download, process, and delete temporary files must be chained together within a single `RUN` instruction using `&&`: `RUN wget massive.tar && compress massive.tar && rm massive.tar` ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Dockerfile instructions like COPY, RUN, and ADD create immutable, read-only layers..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Dockerfile instructions like COPY, RUN, and ADD create immutable, read-only layers.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-73-docker-q67-your-company-is-migrating-stateful-mysql-databases-to-docker-a-consultant-advises-using-bind-mounts-you-disagree-and-advocate-strongly-for-completely-bypassing-the-docker-storage-driver-entirely-by-utilizing-raw-block-devices-why-l3"></a>
### 73. Docker Q67: Your company is migrating stateful MySQL databases to Docker A consultant advises using Bind Mounts You disagree and advocate strongly for completely bypassing the Docker Storage Driver entirely by utilizing raw Block Devices Why [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Docker` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Docker` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"Your company is migrating stateful MySQL databases to Docker. A consultant advises using "Bind Mounts". You disagree and advocate strongly for completely bypassing the Docker Storage Driver entirely by utilizing raw Block Devices. Why?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"During an image optimization initiative across our services, we solved this exact problem. The interviewer is testing: Storage drivers under heavy I/O workloads.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Using standard Docker Storage Drivers (like overlay2) or traversing file-system boundaries for massive, high-IOPS write-heavy database workloads introduces significant systemic overhead. While named volumes heavily bypass the UnionFS, for extreme enterprise database performance (bare-metal equivalence), you should allocate a raw LUN or dedicated partition (e.g., `/dev/sdb`) and map it directly into the container using the `--device` flag, allowing the database engine inside the container to interact directly with the kernel's block layer natively, completely eliminating Docker's storage abstraction penalties. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Using standard Docker Storage Drivers (like overlay2) or traversing file-system boundaries for massive, high-IOPS write-heavy data.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Using standard Docker Storage Drivers (like overlay2) or traversing file-system boundaries for
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-74-docker-q68-you-execute-docker-run-d-myapp-the-terminal-returns-a-long-container-id-but-immediately-upon-checking-docker-ps-the-container-is-completely-missing-docker-ps-a-shows-it-exited-with-code-0-why-did-it-immediately-stop-if-it-didnt-error-l2"></a>
### 74. Docker Q68: You execute docker run -d myapp The terminal returns a long container ID but immediately upon checking docker ps the container is completely missing docker ps -a shows it exited with code 0 Why did it immediately stop if it didnt error [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"You execute `docker run -d myapp`. The terminal returns a long container ID, but immediately upon checking `docker ps`, the container is completely missing. `docker ps -a` shows it exited with code 0. Why did it immediately stop if it didn't error?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Container stability relies on clean signal handling (SIGTERM vs SIGKILL) and immutable image tagging. The interviewer is testing: Daemonizing background processes inside containers.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

A Docker container strictly lives only as long as its primary PID 1 process is running. If the `CMD` or `ENTRYPOINT` in the Dockerfile starts an application in the background (e.g., executing `service nginx start` or appending an `&` to a script), the script will start the daemon, successfully finish its execution, and return an exit code of `0`. Because the foreground script finished, PID 1 terminates, and Docker shuts down the container, killing everything inside it. *Fix:* You must run the main process in the foreground. Use `nginx -g 'daemon off;'` or execute the application binary explicitly without backgrounding it. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: A Docker container strictly lives only as long as its primary PID 1 process is running..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: A Docker container strictly lives only as long as its primary PID 1 process is running.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-75-docker-q69-what-happens-if-your-ci-pipeline-repeatedly-builds-the-exact-same-dockerfile-using-the-latest-tag-and-pushes-it-to-an-aws-ecr-registry-every-day-for-a-year-l1"></a>
### 75. Docker Q69: What happens if your CI pipeline repeatedly builds the exact same Dockerfile using the latest tag and pushes it to an AWS ECR registry every day for a year [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Docker` • `Docker` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Docker` `Docker` `L1` `Containers` `Linux`

> **Interview Question:**  
> *"What happens if your CI pipeline repeatedly builds the exact same Dockerfile using the `latest` tag and pushes it to an AWS ECR registry every day for a year?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When containerizing our microservices stack, container lifecycle and resource management were critical. The interviewer is testing: Tag mutability, dangling references, registry bloat.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Using the `latest` tag makes it a **mutable tag**. Every time the CI pipeline pushes, AWS ECR will overwrite the `latest` tag to point to the brand new image manifest. The older images from previous days will lose their tag and become **Untagged** (Dangling) images in the registry. If no Lifecycle Policy is configured to garbage-collect untagged images, you will accumulate 365 orphaned 1GB images, paying AWS for useless storage bloat. (Also, deploying `latest` in Kubernetes is dangerous as it breaks rollback determinism). Always use Git SHAs or Semantic Versioning tags. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Using the latest tag makes it a mutable tag..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Using the latest tag makes it a mutable tag.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-76-docker-q70-you-want-to-pass-a-highly-sensitive-api-key-to-a-running-container-you-know-not-to-bake-it-into-the-image-so-you-pass-it-as-an-environment-variable-docker-run-e-secret-apikey-why-is-this-still-arguably-a-security-vulnerability-and-what-is-the-better-approach-l3"></a>
### 76. Docker Q70: You want to pass a highly sensitive API key to a running container You know not to bake it into the image so you pass it as an environment variable (docker run -e SECRET=apikey) Why is this still arguably a security vulnerability and what is the better approach [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Docker` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Docker` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"You want to pass a highly sensitive API key to a running container. You know not to bake it into the image, so you pass it as an environment variable (`docker run -e SECRET=apikey`). Why is this still arguably a security vulnerability, and what is the better approach?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In an interview, I explain how we diagnosed container runtime failures without guessing. The interviewer is testing: Secret exposure via `docker inspect` and `procfs`.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Passing secrets via Environment Variables (`-e`) is insecure because:

- Anyone with access to run `docker inspect ` on the host will see the secret in plaintext in the JSON output.
- If the application crashes, the environment variables are often heavily dumped into the error trace logs.
- The variables are exposed physically in the kernel via `/proc//environ`, accessible by any other running process grouped with the same owner.

##### 2️⃣ Remediation & Permanent Safeguards

*Better Approach:* Use Docker Secrets (if in Swarm) or K8s Secrets, which act as a temporary RAM-disk `tmpfs` layer. The secret is securely mounted as a file (e.g., `/run/secrets/apikey`). The application securely reads the file string into memory once, preventing it from appearing in standard diagnostic dumps. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Anyone with access to run docker inspect  on the host will see the secret in plaintext in the JSON output..

#### ⏱️ 60-Second Elevator Pitch Summary

- Anyone with access to run docker inspect  on the host will see the secret in plaintext in the JSO...
- If the application crashes, the environment variables are often heavily dumped into the error tra...
- The variables are exposed physically in the kernel via /proc//environ, accessible by any other ru...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-77-docker-q71-a-heavily-loaded-nginx-container-starts-rejecting-connections-citing-too-many-open-files-you-check-the-host-linux-server-and-its-ulimit-n-is-set-to-1000000-why-is-the-container-still-failing-l2"></a>
### 77. Docker Q71: A heavily loaded Nginx container starts rejecting connections citing Too many open files You check the host Linux server and its ulimit -n is set to 1000000 Why is the container still failing [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Docker` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Docker` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"A heavily loaded Nginx container starts rejecting connections citing "Too many open files". You check the host Linux server, and its `ulimit -n` is set to 1,000,000. Why is the container still failing?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"During an image optimization initiative across our services, we solved this exact problem. The interviewer is testing: Container-specific ulimit enforcement.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Containers do not automatically inherit the `ulimit` settings from the user space of the host operating system. The Docker daemon manages its own default limits for containers (often the conservative 1024 or 4096 standard). To resolve this, you must explicitly pass the ulimits during the container instantiation: `docker run --ulimit nofile=65536:65536 mynginx` Alternatively, you can globally alter the defaults overriding the Docker daemon configuration (`/etc/docker/daemon.json`) so all new containers inherit a more production-ready baseline. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Containers do not automatically inherit the ulimit settings from the user space of the host operating system. The Docker daemon ma.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Containers do not automatically inherit the ulimit settings from the user space of the host ope
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-78-docker-q72-you-are-investigating-an-incident-how-do-you-find-the-exact-time-a-container-was-created-started-and-stopped-down-to-the-millisecond-l1"></a>
### 78. Docker Q72: You are investigating an incident How do you find the exact time a container was created started and stopped down to the millisecond [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Docker` • `Docker` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Docker` `Docker` `L1` `Containers` `Linux`

> **Interview Question:**  
> *"You are investigating an incident. How do you find the exact time a container was created, started, and stopped down to the millisecond?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Container stability relies on clean signal handling (SIGTERM vs SIGKILL) and immutable image tagging. The interviewer is testing: `docker inspect` parsing.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

You would use the `docker inspect` command to query the detailed metadata json. You can parse it cleanly using the go-template format flag: `docker inspect --format='{{.State.StartedAt}} :: {{.State.FinishedAt}}' `. This bypasses manually scrolling through massive JSON outputs. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: You would use the docker inspect command to query the detailed metadata json..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: You would use the docker inspect command to query the detailed metadata json.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-79-docker-q73-your-ci-cd-builds-for-a-massive-go-monorepo-are-taking-20-minutes-because-every-minor-code-change-invalidates-the-run-go-mod-download-layer-forcing-a-re-download-of-gigabytes-of-packages-how-do-you-optimize-the-dockerfile-to-utilize-buildkit-cache-mounts-and-permanently-speed-this-up-l3"></a>
### 79. Docker Q73: Your CI/CD builds for a massive Go monorepo are taking 20 minutes because every minor code change invalidates the RUN go mod download layer forcing a re-download of gigabytes of packages How do you optimize the Dockerfile to utilize BuildKit cache mounts and permanently speed this up [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Docker` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Docker` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"Your CI/CD builds for a massive Go monorepo are taking 20 minutes because every minor code change invalidates the `RUN go mod download` layer, forcing a re-download of gigabytes of packages. How do you optimize the Dockerfile to utilize BuildKit cache mounts and permanently speed this up?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When containerizing our microservices stack, container lifecycle and resource management were critical. The interviewer is testing: Advanced BuildKit features, `--mount=type=cache`.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

You need to use a BuildKit persistent cache mount for the dependency directory. This allows the compiler to share an explicit cache folder across completely different consecutive pipeline builds, independently of the image layer cache. Even if `go.mod` is bumped and the layer invalidates, the persistent cache mount still contains 99% of the previously downloaded packages on disk, reducing the 20-minute download to seconds. ---

```bash
# Must enable BuildKit
COPY go.mod go.sum .
RUN --mount=type=cache,target=/go/pkg/mod \
    go mod download
COPY . .
RUN --mount=type=cache,target=/go/pkg/mod \
    --mount=type=cache,target=/root/.cache/go-build \
    go build -o app
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: You need to use a BuildKit persistent cache mount for the dependency directory. This allows the compiler to share an explicit cach.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: You need to use a BuildKit persistent cache mount for the dependency directory. This allows the
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-80-docker-q74-a-developer-executes-a-docker-run-rm-v-home-user-code-app-mynode-to-run-a-script-containing-npm-install-when-the-container-finishes-the-developer-finds-that-all-the-new-node-modules-files-placed-in-their-home-user-code-folder-are-owned-by-root-why-and-how-do-you-prevent-this-l2"></a>
### 80. Docker Q74: A developer executes a docker run --rm -v /home/user/code/app mynode to run a script containing npm install When the container finishes the developer finds that all the new node_modules files placed in their /home/user/code folder are owned by root Why and how do you prevent this [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Must enable BuildKit` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"A developer executes a `docker run --rm -v /home/user/code:/app mynode` to run a script containing `npm install`. When the container finishes, the developer finds that all the new node_modules files placed in their `/home/user/code` folder are owned by `root`. Why, and how do you prevent this?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In an interview, I explain how we diagnosed container runtime failures without guessing. The interviewer is testing: UID/GID matching across namespaces, volume permission issues.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

By default, processes inside the container execute as the `root` user (UID 0). When those processes write to a bind-mounted directory, they use UID 0 on the host filesystem. Even if you are a regular user on the host, the files are created strictly by root. *Fix:* You must tightly align the executing user. Run the container explicitly with your current UID/GID by passing the `--user` flag: `docker run --rm --user $(id -u):$(id -g) -v $(pwd):/app mynode npm install` The files will then be generated with the exact identical UID/GID mapping back to the host developer. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: By default, processes inside the container execute as the root user (UID 0)..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: By default, processes inside the container execute as the root user (UID 0).
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-81-docker-q75-what-happens-if-you-run-out-of-ips-in-a-docker-bridge-network-how-many-ips-does-the-default-docker-bridge-give-you-by-default-l1"></a>
### 81. Docker Q75: What happens if you run out of IPs in a Docker bridge network How many IPs does the default Docker bridge give you by default [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Docker` `Must enable BuildKit` `L1` `Containers` `Linux`

> **Interview Question:**  
> *"What happens if you run out of IPs in a Docker bridge network? How many IPs does the default Docker bridge give you by default?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"During an image optimization initiative across our services, we solved this exact problem. The interviewer is testing: `docker0` bridge /16 defaults.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

The default `docker0` bridge network utilizes the `172.17.0.0/16` subnet, which provides approximately 65,534 IP addresses. If you miraculously exhaust this or configure a custom network with a smaller `/24` subnet and exhaust it, Docker will vehemently fail to start any new containers on that network, citing an IP Address Allocation error in the daemon logs. You would have to aggressively prune dead containers or recreate the network heavily utilizing a larger CIDR block. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: The default docker0 bridge network utilizes the 172.17.0.0/16 subnet, which provides approximately 65,534 IP addresses..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: The default docker0 bridge network utilizes the 172.17.0.0/16 subnet, which provides approximat
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-82-docker-q76-you-deploy-a-cluster-of-50-identical-microservices-to-ensure-zero-drifts-they-all-pull-a-massive-1gb-initial-configuration-file-from-a-central-s3-bucket-immediately-upon-booting-via-the-cmd-script-why-is-this-an-anti-pattern-in-container-architecture-and-what-is-the-immutable-alternative-l3"></a>
### 82. Docker Q76: You deploy a cluster of 50 identical microservices To ensure zero drifts they all pull a massive 1GB initial configuration file from a central S3 bucket immediately upon booting via the CMD script Why is this an anti-pattern in container architecture and what is the immutable alternative [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Must enable BuildKit` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"You deploy a cluster of 50 identical microservices. To ensure zero drifts, they all pull a massive 1GB initial configuration file from a central S3 bucket immediately upon booting via the `CMD` script. Why is this an anti-pattern in container architecture, and what is the immutable alternative?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Container stability relies on clean signal handling (SIGTERM vs SIGKILL) and immutable image tagging. The interviewer is testing: Immutable infrastructure, startup performance, config-maps.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

This brutally violates the principle of **Immutable Infrastructure** and destroys startup agility. If the S3 bucket goes down, your containers cannot boot. If you deploy 50 pods simultaneously, you abruptly trigger a 50GB spike of completely duplicate network traffic, severely delaying readiness. *Alternative:* Small, rapidly changing configurations should be mounted externally at runtime via **Kubernetes ConfigMaps** or Docker Swarm Configs (which use fast local tmpfs). If the 1GB file is structurally static (like a machine learning model), it must be baked directly into the Docker image tightly during the CI/CD build phase. The image then acts as an immutable, instant-booting artifact universally across environments. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: This brutally violates the principle of Immutable Infrastructure and destroys startup agility..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: This brutally violates the principle of Immutable Infrastructure and destroys startup agility.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-83-docker-q77-what-is-a-dangling-volume-and-how-does-it-happen-l2"></a>
### 83. Docker Q77: What is a Dangling Volume and how does it happen [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Must enable BuildKit` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"What is a "Dangling Volume", and how does it happen?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When containerizing our microservices stack, container lifecycle and resource management were critical. The interviewer is testing: Data persistence lifecycle.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

A **Dangling Volume** is an orphaned Docker volume that is no longer attached to any active or stopped container. It often happens when you delete a container with `docker rm ` but fail to include the `-v` flag, which instructs Docker to seamlessly delete associated anonymous volumes. Alternatively, scaling down a stateful set explicitly orphans explicitly named volumes. Because Docker fundamentally prioritizes data safety, it never deletes volumes aggressively automatically. You must run `docker volume prune` manually to securely flush dangling volumes and recover disk space. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: A Dangling Volume is an orphaned Docker volume that is no longer attached to any active or stopped container..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: A Dangling Volume is an orphaned Docker volume that is no longer attached to any active or stop
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-84-docker-q78-are-docker-containers-fundamentally-virtual-machines-defend-your-answer-l1"></a>
### 84. Docker Q78: Are Docker containers fundamentally virtual machines Defend your answer [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Docker` `Must enable BuildKit` `L1` `Containers` `Linux`

> **Interview Question:**  
> *"Are Docker containers fundamentally "virtual machines"? Defend your answer."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In an interview, I explain how we diagnosed container runtime failures without guessing. The interviewer is testing: Core virtualization vs containerization paradigms.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

No, Docker containers natively are **not** Virtual Machines. A VM relies on a heavily hardware-level Hypervisor (like VMware or KVM) to run an entirely distinct, massive Guest Operating System (with its own kernel) for every application. A Docker container uses OS-level virtualization. It tightly shares the exact single underlying Host OS kernel with other containers. It isolates processes locally using Linux features like `Namespaces` (for isolating visibility of network/PIDs) and `Cgroups` (for capping CPU/Memory limits). Containers are vastly lighter because they don't load a 1GB kernel to simply run a 50MB Python app. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: No, Docker containers natively are not Virtual Machines..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: No, Docker containers natively are not Virtual Machines.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-85-docker-q79-youve-developed-an-internal-tool-specifically-for-your-sre-team-using-python-due-to-compliance-you-must-heavily-sign-all-your-docker-images-cryptographically-to-prove-they-originated-exclusively-from-your-exact-ci-cd-server-before-production-will-run-them-what-docker-technology-enforces-this-l3"></a>
### 85. Docker Q79: Youve developed an internal tool specifically for your SRE team using Python Due to compliance you must heavily sign all your Docker images cryptographically to prove they originated exclusively from your exact CI/CD server before production will run them What Docker technology enforces this [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Must enable BuildKit` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"You've developed an internal tool specifically for your SRE team using Python. Due to compliance, you must heavily sign all your Docker images cryptographically to prove they originated exclusively from your exact CI/CD server before production will run them. What Docker technology enforces this?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"During an image optimization initiative across our services, we solved this exact problem. The interviewer is testing: Docker Trust, Notary, sigstore/cosign.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

This is historically managed by **Docker Content Trust (DCT)**, effectively backed by the Notary service. By enabling `export DOCKER_CONTENT_TRUST=1`, the Docker client cryptographically signs the image manifest using private keys before pushing. Production nodes strictly configured with DCT enabled will adamantly refuse to pull or run images missing signatures from trusted cryptographic publishers. Modern approaches strongly lean towards utilizing **Sigstore/Cosign**, which enables keyless signing tied to strict OIDC identities (like GitHub Actions workflows) to sign images seamlessly and generate indisputable transparency logs. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: This is historically managed by Docker Content Trust (DCT), effectively backed by the Notary service. By enabling export DOCKER_CO.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: This is historically managed by Docker Content Trust (DCT), effectively backed by the Notary se
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-86-docker-q80-a-junior-engineer-asks-why-they-cant-effectively-run-a-windows-exe-binary-inside-a-standardized-ubuntu-docker-container-running-natively-on-a-windows-10-host-using-docker-desktop-explain-the-architecture-constraint-l2"></a>
### 86. Docker Q80: A junior engineer asks why they cant effectively run a Windows exe binary inside a standardized Ubuntu Docker container running natively on a Windows 10 host using Docker Desktop Explain the architecture constraint [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Must enable BuildKit` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"A junior engineer asks why they can't effectively run a Windows `.exe` binary inside a standardized Ubuntu Docker container running natively on a Windows 10 host using Docker Desktop. Explain the architecture constraint."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Container stability relies on clean signal handling (SIGTERM vs SIGKILL) and immutable image tagging. The interviewer is testing: Environment isolation, Kernel dependencies vs. Host OS functionality.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Docker Desktop on Windows heavily masks the truth. To run Linux containers, it actually boots a hidden Linux VM deeply in the background (via WSL2 or Hyper-V). The standard "Ubuntu" container runs atop that actual Linux kernel. You cannot run a Windows `.exe` heavily inside a Linux container because the `.exe` file format fundamentally requires Windows APIs, Windows DLLs, and a native Windows NT kernel. Containers only bundle user-space libraries; they *strictly share* the actively running bare-metal kernel. To run a `.exe` in a container, you must use **Windows Server Containers**, which use a native Windows kernel and natively wrap the `.exe` perfectly. You cannot cross-pollinate kernels. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Docker Desktop on Windows heavily masks the truth. To run Linux containers, it actually boots a hidden Linux VM deeply in the back.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Docker Desktop on Windows heavily masks the truth. To run Linux containers, it actually boots a
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-87-docker-q81-you-are-running-a-sidecar-monitoring-agent-alongside-your-main-application-container-using-docker-compose-the-agent-needs-to-see-all-the-processes-running-inside-the-main-application-container-using-ps-aux-by-default-it-can-only-see-its-own-processes-how-do-you-solve-this-l3"></a>
### 87. Docker Q81: You are running a sidecar monitoring agent alongside your main application container using Docker Compose The agent needs to see all the processes running inside the main application container using ps aux By default it can only see its own processes How do you solve this [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Must enable BuildKit` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"You are running a sidecar monitoring agent alongside your main application container using Docker Compose. The agent needs to see all the processes running inside the main application container using `ps aux`. By default, it can only see its own processes. How do you solve this?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When containerizing our microservices stack, container lifecycle and resource management were critical. The interviewer is testing: PID namespace sharing between containers.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

By default, every Docker container gets its own isolated PID namespace, meaning each container can only see its own processes (its PID 1 and descendants). To allow the monitoring sidecar to observe the main application's processes, you must share the PID namespace between the two containers using the `pid` option: With `pid: "service:app"`, the monitor container joins the PID namespace of the `app` container and can see all of its processes via `ps aux` or `/proc`. In plain Docker CLI: `docker run --pid=container:main-app monitoring-agent`. ---

```bash
services:
  app:
    image: myapp
    container_name: main-app

  monitor:
    image: monitoring-agent
    pid: "service:app"
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: By default, every Docker container gets its own isolated PID namespace, meaning each container can only see its own processes (its.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: By default, every Docker container gets its own isolated PID namespace, meaning each container
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-88-docker-q82-a-developer-runs-a-containerized-application-that-writes-millions-of-tiny-temporary-cache-files-during-processing-after-a-few-hours-the-container-crashes-with-no-space-left-on-device-even-though-docker-stats-shows-plenty-of-disk-available-what-is-happening-l2"></a>
### 88. Docker Q82: A developer runs a containerized application that writes millions of tiny temporary cache files during processing After a few hours the container crashes with No space left on device even though docker stats shows plenty of disk available What is happening [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Must enable BuildKit` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"A developer runs a containerized application that writes millions of tiny temporary cache files during processing. After a few hours, the container crashes with "No space left on device" even though `docker stats` shows plenty of disk available. What is happening?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In an interview, I explain how we diagnosed container runtime failures without guessing. The interviewer is testing: tmpfs mounts, inode exhaustion vs. disk space.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

The container is likely running out of **inodes**, not disk space. The overlay2 filesystem has a finite number of inodes, and millions of small files can exhaust the inode table before consuming significant disk bytes. `df -i` inside the container will confirm this. *Fix:* For temporary cache files that don't need to persist, use a **tmpfs mount** which stores data entirely in RAM and doesn't consume inodes from the overlay filesystem: `docker run --tmpfs /app/cache:rw,size=512m myapp` Alternatively, if the cache needs disk backing, mount a dedicated volume (`-v cache-vol:/app/cache`) that has its own independent inode table separate from the container's root filesystem. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: The container is likely running out of inodes, not disk space. The overlay2 filesystem has a finite number of inodes, and millions.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: The container is likely running out of inodes, not disk space. The overlay2 filesystem has a fi
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-89-docker-q83-your-company-has-a-local-docker-registry-a-staging-registry-on-gcp-artifact-registry-and-a-production-registry-on-aws-ecr-a-developer-complains-about-constantly-running-docker-login-and-docker-logout-to-switch-between-them-what-is-the-cleaner-approach-l2"></a>
### 89. Docker Q83: Your company has a local Docker registry a staging registry on GCP Artifact Registry and a production registry on AWS ECR A developer complains about constantly running docker login and docker logout to switch between them What is the cleaner approach [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Must enable BuildKit` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"Your company has a local Docker registry, a staging registry on GCP Artifact Registry, and a production registry on AWS ECR. A developer complains about constantly running `docker login` and `docker logout` to switch between them. What is the cleaner approach?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"During an image optimization initiative across our services, we solved this exact problem. The interviewer is testing: Docker context and credential helpers.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Docker stores credentials per registry in `~/.docker/config.json`, and you do NOT need to log out of one registry to use another. Each `docker login ` adds a separate credential entry. You can push and pull from multiple registries simultaneously without switching. However, for managing different Docker *daemon endpoints* (local vs. remote hosts), use **Docker Contexts**: `docker context create staging --docker "host=tcp://staging-host:2376"` then `docker context use staging`. For the credential management side, configure **credential helpers** (`docker-credential-ecr-login` for AWS, `docker-credential-gcr` for GCP) in `config.json` so authentication tokens auto-refresh without manual `docker login` at all. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Docker stores credentials per registry in ~/.docker/config.json, and you do NOT need to log out of one registry to use another. Ea.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Docker stores credentials per registry in ~/.docker/config.json, and you do NOT need to log out
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-90-docker-q84-a-containerized-microservice-makes-http-calls-to-apiexamplecom-it-works-perfectly-when-tested-locally-on-a-developer-laptop-but-fails-with-dns-resolution-errors-when-deployed-inside-a-docker-container-on-the-ci-server-the-ci-server-itself-can-resolve-the-domain-fine-what-is-wrong-l2"></a>
### 90. Docker Q84: A containerized microservice makes HTTP calls to apiexamplecom It works perfectly when tested locally on a developer laptop but fails with DNS resolution errors when deployed inside a Docker container on the CI server The CI server itself can resolve the domain fine What is wrong [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Must enable BuildKit` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"A containerized microservice makes HTTP calls to `api.example.com`. It works perfectly when tested locally on a developer laptop, but fails with DNS resolution errors when deployed inside a Docker container on the CI server. The CI server itself can resolve the domain fine. What is wrong?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Container stability relies on clean signal handling (SIGTERM vs SIGKILL) and immutable image tagging. The interviewer is testing: Container DNS resolution, Docker's embedded DNS server.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Docker containers on user-defined networks use Docker's embedded DNS server (`127.0.0.11`). On the default bridge network, containers inherit the host's `/etc/resolv.conf`. However, if the host uses `127.0.0.53` (systemd-resolved's stub resolver), Docker copies this into the container where it's meaningless because the container cannot reach the host's loopback address.

- Per container: `docker run --dns 8.8.8.8 myapp`
- Globally in `/etc/docker/daemon.json`: `{"dns": ["8.8.8.8", "8.8.4.4"]}`
- Or switch the CI server's systemd-resolved to expose on a real interface rather than the loopback stub.

##### 2️⃣ Remediation & Permanent Safeguards

*Fix:* Explicitly configure DNS for the container or Docker daemon: ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Per container: docker run --dns 8.8.8.8 myapp.

#### ⏱️ 60-Second Elevator Pitch Summary

- Per container: docker run --dns 8.8.8.8 myapp
- Globally in /etc/docker/daemon.json: {"dns": ["8.8.8.8", "8.8.4.4"]}
- Or switch the CI server's systemd-resolved to expose on a real interface rather than the loopback...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-91-docker-q85-after-months-of-daily-docker-builds-your-production-servers-disk-is-full-you-run-docker-system-prune-af-and-reclaim-some-space-but-the-disk-is-still-90-full-docker-system-df-shows-minimal-usage-where-is-the-hidden-disk-consumption-l3"></a>
### 91. Docker Q85: After months of daily Docker builds your production servers disk is full You run docker system prune -af and reclaim some space but the disk is still 90% full docker system df shows minimal usage Where is the hidden disk consumption [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Must enable BuildKit` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"After months of daily Docker builds, your production server's disk is full. You run `docker system prune -af` and reclaim some space, but the disk is still 90% full. `docker system df` shows minimal usage. Where is the hidden disk consumption?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When containerizing our microservices stack, container lifecycle and resource management were critical. The interviewer is testing: overlay2 layer directory orphans, `/var/lib/docker` internals.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`docker system prune` only removes objects tracked by the Docker daemon (images, containers, volumes, build cache). If the Docker daemon crashed or was force-killed during container operations, orphaned layer directories can accumulate in `/var/lib/docker/overlay2/` that the daemon no longer tracks. *Diagnosis:* Run `du -sh /var/lib/docker/overlay2/` and compare with `docker system df`. A large discrepancy confirms orphaned layers. *Fix:* The safest approach is to stop the Docker daemon (`systemctl stop docker`), back up any critical volumes, and reset the storage entirely (`rm -rf /var/lib/docker`). Restarting Docker recreates the directory structure. Re-pull needed images. For prevention, ensure the Docker daemon shuts down gracefully and monitor `/var/lib/docker` disk usage independently. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: docker system prune only removes objects tracked by the Docker daemon (images, containers, volumes, build cache). If the Docker da.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: docker system prune only removes objects tracked by the Docker daemon (images, containers, volu
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-92-docker-q86-your-security-team-mandates-that-docker-must-run-without-root-privileges-on-all-developer-workstations-the-developers-still-need-full-docker-build-and-run-capabilities-how-do-you-achieve-this-l3"></a>
### 92. Docker Q86: Your security team mandates that Docker must run without root privileges on all developer workstations The developers still need full Docker build and run capabilities How do you achieve this [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Must enable BuildKit` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"Your security team mandates that Docker must run without root privileges on all developer workstations. The developers still need full Docker build and run capabilities. How do you achieve this?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In an interview, I explain how we diagnosed container runtime failures without guessing. The interviewer is testing: Rootless Docker mode.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use **Rootless Docker**, which runs the Docker daemon and all containers entirely within a user's namespace without requiring root privileges on the host. Installation: `dockerd-rootless-setuptool.sh install` (ships with Docker 20.10+). The daemon runs as the user's systemd service, stores data under `~/.local/share/docker/`, and maps UIDs using `newuidmap`/`newgidmap` (requires `/etc/subuid` and `/etc/subgid` entries). *Limitations:* Cannot bind to privileged ports (<1024) without `CAP_NET_BIND_SERVICE`. `--net=host` doesn't work. Overlay networks require kernel 5.11+ with unprivileged overlay support. Some storage drivers may have reduced performance. Despite these trade-offs, rootless Docker satisfies the security mandate while preserving standard build and run workflows. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use Rootless Docker, which runs the Docker daemon and all containers entirely within a user's namespace without requiring root pri.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use Rootless Docker, which runs the Docker daemon and all containers entirely within a user's n
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-93-docker-q87-your-ci-pipeline-runs-unit-tests-inside-a-docker-build-using-a-multi-stage-dockerfile-if-the-tests-fail-you-want-to-extract-the-test-report-junit-xml-from-the-failed-build-stage-but-docker-build-exits-with-an-error-and-produces-no-final-image-how-do-you-get-the-test-report-out-l2"></a>
### 93. Docker Q87: Your CI pipeline runs unit tests inside a Docker build using a multi-stage Dockerfile If the tests fail you want to extract the test report (JUnit XML) from the failed build stage But docker build exits with an error and produces no final image How do you get the test report out [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Must enable BuildKit` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"Your CI pipeline runs unit tests inside a Docker build using a multi-stage Dockerfile. If the tests fail, you want to extract the test report (JUnit XML) from the failed build stage. But `docker build` exits with an error and produces no final image. How do you get the test report out?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"During an image optimization initiative across our services, we solved this exact problem. The interviewer is testing: Multi-stage build targets, `--target` flag.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use the `--target` flag to build only up to the test stage, and structure the Dockerfile so the test report is generated *before* the assertion that causes the build to fail: Build with: `docker build --target test -o type=local,dest=./output .` using BuildKit's `--output` flag. Even if the full build fails, you can separately export just the test stage output. Alternatively, use `docker create` on the test target image and `docker cp` the report out. ---

```bash
FROM golang:1.21 AS test
COPY . .
RUN go test -v ./... -count=1 2>&1 | go-junit-report > /report.xml; \
    go test ./... -count=1

FROM alpine AS runtime
COPY --from=test /app/binary /app/binary
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use the --target flag to build only up to the test stage, and structure the Dockerfile so the test report is generated *before* th.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use the --target flag to build only up to the test stage, and structure the Dockerfile so the t
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-94-docker-q88-a-production-container-running-an-api-gateway-is-performing-well-but-you-notice-its-writable-layer-is-growing-by-500mb-per-day-the-application-itself-doesnt-write-data-to-disk-intentionally-what-is-causing-the-growth-and-how-do-you-stop-it-l2"></a>
### 94. Docker Q88: A production container running an API gateway is performing well but you notice its writable layer is growing by 500MB per day The application itself doesnt write data to disk intentionally What is causing the growth and how do you stop it [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Must enable BuildKit` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"A production container running an API gateway is performing well but you notice its writable layer is growing by 500MB per day. The application itself doesn't write data to disk intentionally. What is causing the growth and how do you stop it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Container stability relies on clean signal handling (SIGTERM vs SIGKILL) and immutable image tagging. The interviewer is testing: Container writable layer, log files, and read-only filesystem.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

The application or its runtime is writing files to the container's writable layer (the thin read-write layer on top of the image layers). Common culprits: application logs not sent to stdout, temp files, DNS resolver cache, or library-generated cache files.

- Redirect all logs to stdout/stderr instead of files.
- Mount writable paths as volumes or tmpfs so writes bypass the container layer.
- Run the container with a **read-only root filesystem**: `docker run --read-only --tmpfs /tmp --tmpfs /var/run myapp`. This forces you to explicitly declare every writable path, preventing unexpected layer growth.

##### 2️⃣ Remediation & Permanent Safeguards

*Diagnosis:* Run `docker diff ` to see every file added (`A`), changed (`C`), or deleted (`D`) in the writable layer since the container started. *Fix:* ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Redirect all logs to stdout/stderr instead of files..

#### ⏱️ 60-Second Elevator Pitch Summary

- Redirect all logs to stdout/stderr instead of files.
- Mount writable paths as volumes or tmpfs so writes bypass the container layer.
- Run the container with a read-only root filesystem: docker run --read-only --tmpfs /tmp --tmpfs /...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-95-docker-q89-your-ci-pipeline-runs-dockerized-build-jobs-that-themselves-need-to-build-docker-images-docker-in-docker-the-team-currently-mounts-the-host-docker-socket-var-run-dockersock-the-security-team-rejects-this-what-are-the-alternatives-l3"></a>
### 95. Docker Q89: Your CI pipeline runs Dockerized build jobs that themselves need to build Docker images (Docker-in-Docker) The team currently mounts the host Docker socket (/var/run/dockersock) The security team rejects this What are the alternatives [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Must enable BuildKit` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"Your CI pipeline runs Dockerized build jobs that themselves need to build Docker images (Docker-in-Docker). The team currently mounts the host Docker socket (`/var/run/docker.sock`). The security team rejects this. What are the alternatives?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When containerizing our microservices stack, container lifecycle and resource management were critical. The interviewer is testing: Docker-in-Docker alternatives, Kaniko, Buildah.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Mounting the Docker socket gives the inner container full root-equivalent access to the host. Secure alternatives:

- **Kaniko** — Google's tool that builds container images from a Dockerfile *inside* a container without requiring a Docker daemon. It executes each Dockerfile command in userspace, produces an OCI image, and pushes directly to a registry. Runs unprivileged. Ideal for Kubernetes-based CI (Tekton, GitLab Runner).
- **Buildah** — Builds OCI images without a daemon. Can run rootless. Supports Dockerfile syntax and its own native commands.
- **Docker-in-Docker (dind)** — Run a full Docker daemon inside a privileged container. More secure than socket mounting (isolated daemon), but still requires `--privileged`. Use only when Kaniko/Buildah can't satisfy the use case.

##### 2️⃣ Remediation & Permanent Safeguards

---

- **BuildKit with remote builder** — Run BuildKit as a separate service and point `docker buildx` at it remotely: `docker buildx create --driver remote --name mybuilder tcp://buildkit:1234`.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Kaniko — Google's tool that builds container images from a Dockerfile *inside* a container without requiring a Docker daemon. It e.

#### ⏱️ 60-Second Elevator Pitch Summary

- Kaniko — Google's tool that builds container images from a Dockerfile *inside* a container withou...
- Buildah — Builds OCI images without a daemon. Can run rootless. Supports Dockerfile syntax and it...
- Docker-in-Docker (dind) — Run a full Docker daemon inside a privileged container. More secure tha...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-96-docker-q90-a-container-running-nginx-generates-enormous-log-files-and-eventually-fills-the-disk-on-the-docker-host-you-want-docker-to-automatically-handle-log-rotation-without-modifying-the-nginx-configuration-how-l2"></a>
### 96. Docker Q90: A container running Nginx generates enormous log files and eventually fills the disk on the Docker host You want Docker to automatically handle log rotation without modifying the Nginx configuration How [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Must enable BuildKit` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"A container running Nginx generates enormous log files and eventually fills the disk on the Docker host. You want Docker to automatically handle log rotation without modifying the Nginx configuration. How?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In an interview, I explain how we diagnosed container runtime failures without guessing. The interviewer is testing: Docker logging driver configuration, log rotation.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Docker's default `json-file` logging driver stores container stdout/stderr as JSON files under `/var/lib/docker/containers//`. Without limits, these files grow unbounded. Configure log rotation at the container level: Or set it globally in `/etc/docker/daemon.json`: This rotates logs at 50MB per file and keeps a maximum of 5 rotated files (250MB total per container). For Docker Compose, use the `logging:` key under each service. Note: changing the global config only affects *newly created* containers, not existing ones. ---

```bash
docker run --log-opt max-size=50m --log-opt max-file=5 nginx
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Docker's default json-file logging driver stores container stdout/stderr as JSON files under /var/lib/docker/containers//. Without.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Docker's default json-file logging driver stores container stdout/stderr as JSON files under /v
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-97-docker-q91-you-deploy-a-financial-application-container-and-the-compliance-team-requires-that-the-containers-filesystem-must-be-completely-immutable-at-runtime-no-process-should-be-able-to-write-anywhere-except-explicitly-approved-paths-how-do-you-enforce-this-l3"></a>
### 97. Docker Q91: You deploy a financial application container and the compliance team requires that the containers filesystem must be completely immutable at runtime — no process should be able to write anywhere except explicitly approved paths How do you enforce this [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Must enable BuildKit` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"You deploy a financial application container and the compliance team requires that the container's filesystem must be completely immutable at runtime — no process should be able to write anywhere except explicitly approved paths. How do you enforce this?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"During an image optimization initiative across our services, we solved this exact problem. The interviewer is testing: Read-only root filesystem, defense-in-depth.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use the `--read-only` flag to make the entire root filesystem read-only: With `--read-only`, any write attempt to an unmounted path returns a "Read-only file system" error. You explicitly whitelist writable paths using `tmpfs` (ephemeral, in-memory) or named volumes (persistent). The `noexec` and `nosuid` flags on tmpfs add additional hardening. In Kubernetes, set `readOnlyRootFilesystem: true` in the `securityContext`. Combine this with `allowedHostPaths` in PodSecurityPolicy or a Kyverno/OPA policy to restrict volume mounts. This approach follows the principle of least privilege and prevents attackers from writing backdoor binaries even if they compromise the application. ---

```bash
docker run --read-only \
  --tmpfs /tmp:rw,noexec,nosuid,size=100m \
  --tmpfs /var/run:rw,size=10m \
  -v logs-vol:/var/log \
  myfinancialapp
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use the --read-only flag to make the entire root filesystem read-only:.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use the --read-only flag to make the entire root filesystem read-only:
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-98-docker-q92-your-team-wants-to-implement-live-migration-of-a-running-docker-container-from-one-host-to-another-without-stopping-it-similar-to-vm-live-migration-is-this-possible-with-docker-what-technology-enables-it-l3"></a>
### 98. Docker Q92: Your team wants to implement live migration of a running Docker container from one host to another without stopping it similar to VM live migration Is this possible with Docker What technology enables it [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Must enable BuildKit` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"Your team wants to implement live migration of a running Docker container from one host to another without stopping it, similar to VM live migration. Is this possible with Docker? What technology enables it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Container stability relies on clean signal handling (SIGTERM vs SIGKILL) and immutable image tagging. The interviewer is testing: CRIU (Checkpoint/Restore in Userspace), container migration limitations.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Docker has experimental support for **checkpoint and restore** using **CRIU (Checkpoint/Restore In Userspace)**. CRIU freezes a running process, serializes its entire state (memory, registers, open files, sockets, timers) to disk, and can restore it later — even on a different host.

- Checkpoint: `docker checkpoint create  checkpoint1`
- Transfer the checkpoint data and container filesystem to the target host.
- Restore: `docker start --checkpoint checkpoint1 `

##### 2️⃣ Remediation & Permanent Safeguards

Workflow: *Limitations:* This feature is experimental and not production-ready. Open network connections break (TCP state doesn't survive cross-host migration). External storage must be shared (e.g., NFS). GPU state, complex IPC, and certain kernel features aren't fully supported. For production workloads, Kubernetes pod rescheduling with graceful shutdown/startup is the practical alternative. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Checkpoint: docker checkpoint create  checkpoint1.

#### ⏱️ 60-Second Elevator Pitch Summary

- Checkpoint: docker checkpoint create  checkpoint1
- Transfer the checkpoint data and container filesystem to the target host.
- Restore: docker start --checkpoint checkpoint1

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-99-docker-q93-a-developer-has-a-project-with-a-10gb-data-directory-containing-training-datasets-every-docker-build-takes-15-minutes-before-even-executing-the-first-dockerfile-instruction-the-dockerfile-doesnt-reference-the-data-directory-at-all-why-is-it-so-slow-l2"></a>
### 99. Docker Q93: A developer has a project with a 10GB data/ directory containing training datasets Every docker build takes 15 minutes before even executing the first Dockerfile instruction The Dockerfile doesnt reference the data/ directory at all Why is it so slow [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Must enable BuildKit` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"A developer has a project with a 10GB `data/` directory containing training datasets. Every `docker build` takes 15 minutes before even executing the first Dockerfile instruction. The Dockerfile doesn't reference the `data/` directory at all. Why is it so slow?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When containerizing our microservices stack, container lifecycle and resource management were critical. The interviewer is testing: Docker build context transfer, `.dockerignore`.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Before executing any Dockerfile instruction, Docker packages the entire **build context** (the directory passed to `docker build`) and transfers it to the Docker daemon. If the `data/` directory is inside the build context, Docker transfers all 10GB every single build — even though no `COPY` or `ADD` references it. The "Sending build context to Docker daemon... 10GB" message in the build output confirms this. *Fix:* Add `data/` to `.dockerignore`: This reduces the build context to only the files the Dockerfile actually needs. Alternatively, restructure the project so the Dockerfile lives in a subdirectory without the data, or use BuildKit's ability to specify individual files via `--build-context`. ---

```bash
data/
*.csv
*.parquet
__pycache__/
.git/
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Before executing any Dockerfile instruction, Docker packages the entire build context (the directory passed to docker build) and t.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Before executing any Dockerfile instruction, Docker packages the entire build context (the dire
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-100-docker-q94-your-docker-compose-file-defines-15-services-but-during-local-development-you-only-need-4-of-them-running-starting-all-15-wastes-resources-and-slows-down-your-machine-how-do-you-selectively-start-subsets-of-services-without-maintaining-multiple-compose-files-l2"></a>
### 100. Docker Q94: Your Docker Compose file defines 15 services but during local development you only need 4 of them running Starting all 15 wastes resources and slows down your machine How do you selectively start subsets of services without maintaining multiple Compose files [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Must enable BuildKit` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"Your Docker Compose file defines 15 services, but during local development, you only need 4 of them running. Starting all 15 wastes resources and slows down your machine. How do you selectively start subsets of services without maintaining multiple Compose files?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In an interview, I explain how we diagnosed container runtime failures without guessing. The interviewer is testing: Docker Compose profiles.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Use **Compose Profiles** (introduced in Docker Compose v1.28):

- `docker compose up` — starts only services without profiles (api).
- `docker compose --profile backend up` — starts api + worker.
- `docker compose --profile full up` — starts everything.

##### 2️⃣ Remediation & Permanent Safeguards

Services without a `profiles` key always start. Services with profiles only start when that profile is explicitly activated: This is cleaner than `docker compose up service1 service2` because profiles logically group related services and can be combined. ---

```bash
services:
  api:
    image: myapi
    # No profile = always starts

  worker:
    image: myworker
    profiles: ["full", "backend"]

  ml-engine:
    image: ml-engine
    profiles: ["full", "ml"]

  monitoring:
    image: grafana
    profiles: ["full", "debug"]
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: docker compose up — starts only services without profiles (api)..

#### ⏱️ 60-Second Elevator Pitch Summary

- docker compose up — starts only services without profiles (api).
- docker compose --profile backend up — starts api + worker.
- docker compose --profile full up — starts everything.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-101-docker-q95-a-containerized-application-needs-to-call-an-api-server-running-directly-on-the-docker-host-machine-not-in-a-container-using-localhost-or-127001-from-inside-the-container-doesnt-work-how-does-the-container-reach-the-host-l2"></a>
### 101. Docker Q95: A containerized application needs to call an API server running directly on the Docker host machine (not in a container) Using localhost or 127001 from inside the container doesnt work How does the container reach the host [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Must enable BuildKit` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"A containerized application needs to call an API server running directly on the Docker host machine (not in a container). Using `localhost` or `127.0.0.1` from inside the container doesn't work. How does the container reach the host?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"During an image optimization initiative across our services, we solved this exact problem. The interviewer is testing: Container-to-host networking, `host.docker.internal`.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Inside a container, `localhost` refers to the container's own loopback interface, not the host's. The container and host have separate network namespaces.

- **Docker Desktop (Mac/Windows):** Use the special DNS name `host.docker.internal`, which automatically resolves to the host machine's internal IP. Available out of the box.
- **Docker Engine on Linux (20.10+):** Add `--add-host=host.docker.internal:host-gateway` to the run command. `host-gateway` is a special string that Docker resolves to the host's gateway IP (typically `172.17.0.1`).
- **Docker Compose:**

##### 2️⃣ Remediation & Permanent Safeguards

*Solutions:* ---

- **`--network=host`** mode eliminates the network namespace boundary entirely, but sacrifices container isolation.

```bash
services:
  app:
    image: myapp
    extra_hosts:
      - "host.docker.internal:host-gateway"
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Docker Desktop (Mac/Windows): Use the special DNS name host.docker.internal, which automatically resolves to the host machine's in.

#### ⏱️ 60-Second Elevator Pitch Summary

- Docker Desktop (Mac/Windows): Use the special DNS name host.docker.internal, which automatically ...
- Docker Engine on Linux (20.10+): Add --add-host=host.docker.internal:host-gateway to the run comm...
- Docker Compose:

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-102-docker-q96-your-ci-pipeline-suddenly-starts-failing-with-toomanyrequests-you-have-reached-your-pull-rate-limit-errors-when-pulling-base-images-from-docker-hub-what-is-happening-and-how-do-you-fix-it-l2"></a>
### 102. Docker Q96: Your CI pipeline suddenly starts failing with toomanyrequests You have reached your pull rate limit errors when pulling base images from Docker Hub What is happening and how do you fix it [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Must enable BuildKit` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"Your CI pipeline suddenly starts failing with "toomanyrequests: You have reached your pull rate limit" errors when pulling base images from Docker Hub. What is happening and how do you fix it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Container stability relies on clean signal handling (SIGTERM vs SIGKILL) and immutable image tagging. The interviewer is testing: Docker Hub rate limits, registry mirrors.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Docker Hub enforces pull rate limits: anonymous users get 100 pulls per 6 hours per IP, authenticated free users get 200. CI servers sharing a single public IP exhaust this quickly.

- **Authenticate:** `docker login` with a Docker Hub account in CI — doubles the limit and tracks per-account instead of per-IP.
- **Docker Hub Pro/Team subscription** — removes rate limits entirely.
- **Registry Mirror/Proxy Cache:** Set up a pull-through cache using a local registry: `docker run -d -e REGISTRY_PROXY_REMOTEURL=https://registry-1.docker.io registry:2`. Configure the Docker daemon to use this mirror in `/etc/docker/daemon.json`: `{"registry-mirrors": ["http://localhost:5000"]}`. Subsequent pulls hit the local cache.

##### 2️⃣ Remediation & Permanent Safeguards

*Fixes:* ---

- **Copy base images** to your private registry (ECR/GCR/ACR) and reference them from there. This completely eliminates Docker Hub dependency.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Authenticate: docker login with a Docker Hub account in CI — doubles the limit and tracks per-account instead of per-IP..

#### ⏱️ 60-Second Elevator Pitch Summary

- Authenticate: docker login with a Docker Hub account in CI — doubles the limit and tracks per-acc...
- Docker Hub Pro/Team subscription — removes rate limits entirely.
- Registry Mirror/Proxy Cache: Set up a pull-through cache using a local registry: docker run -d -e...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-103-docker-q97-you-need-to-verify-whether-a-docker-image-tagged-myappv210-in-your-registry-is-truly-a-multi-architecture-image-that-supports-both-linux-amd64-and-linux-arm64-without-pulling-the-entire-image-how-do-you-inspect-this-remotely-l3"></a>
### 103. Docker Q97: You need to verify whether a Docker image tagged myappv210 in your registry is truly a multi-architecture image that supports both linux/amd64 and linux/arm64 without pulling the entire image How do you inspect this remotely [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Must enable BuildKit` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"You need to verify whether a Docker image tagged `myapp:v2.1.0` in your registry is truly a multi-architecture image that supports both `linux/amd64` and `linux/arm64`, without pulling the entire image. How do you inspect this remotely?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When containerizing our microservices stack, container lifecycle and resource management were critical. The interviewer is testing: OCI image manifests, manifest lists, `docker manifest inspect`.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use `docker manifest inspect` to query the registry's manifest list without downloading any image layers: For a multi-arch image, this returns a **manifest list** (also called a "fat manifest") containing multiple entries — one per platform. Each entry specifies the `architecture`, `os`, and a digest pointing to the platform-specific image manifest. If the image is single-architecture, the command returns a single image manifest with layer digests instead of a list. You can also use tools like **crane** (from Google's go-containerregistry): Or **skopeo**: `skopeo inspect --raw docker://myregistry.com/myapp:v2.1.0 | jq .` These tools query the registry API directly, never downloading image layers. ---

```bash
docker manifest inspect myregistry.com/myapp:v2.1.0
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use docker manifest inspect to query the registry's manifest list without downloading any image layers:.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use docker manifest inspect to query the registry's manifest list without downloading any image
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-104-docker-q98-you-run-a-shell-script-as-the-entrypoint-that-spawns-multiple-background-worker-processes-when-you-docker-stop-the-container-it-always-takes-exactly-10-seconds-the-timeout-before-stopping-and-the-workers-dont-clean-up-properly-what-is-the-root-cause-l2"></a>
### 104. Docker Q98: You run a shell script as the ENTRYPOINT that spawns multiple background worker processes When you docker stop the container it always takes exactly 10 seconds (the timeout) before stopping and the workers dont clean up properly What is the root cause [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Must enable BuildKit` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"You run a shell script as the ENTRYPOINT that spawns multiple background worker processes. When you `docker stop` the container, it always takes exactly 10 seconds (the timeout) before stopping, and the workers don't clean up properly. What is the root cause?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In an interview, I explain how we diagnosed container runtime failures without guessing. The interviewer is testing: Signal handling, PID 1 behavior, `exec` in entrypoint scripts.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

When Docker sends `SIGTERM` via `docker stop`, it delivers the signal to PID 1 inside the container. If PID 1 is a shell script (`/bin/sh` or `/bin/bash`), the shell does NOT forward signals to its child processes by default. The shell itself ignores `SIGTERM`, so nothing happens for 10 seconds until Docker sends `SIGKILL`.

- **Use `exec`** to replace the shell with the main process: the last line of your entrypoint script should be `exec ./my-worker` instead of `./my-worker`. This makes the worker PID 1 and it receives `SIGTERM` directly.
- **Trap signals** in the shell script if you must manage multiple processes:
- **Use `--init`** flag (`docker run --init`) to inject `tini` as PID 1, which properly forwards signals and reaps zombie processes.

##### 2️⃣ Remediation & Permanent Safeguards

*Fixes:* ---

```bash
#!/bin/bash
trap 'kill $(jobs -p); wait' SIGTERM SIGINT
./worker1 &
./worker2 &
wait
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use exec to replace the shell with the main process: the last line of your entrypoint script should be exec ./my-worker instead of.

#### ⏱️ 60-Second Elevator Pitch Summary

- Use exec to replace the shell with the main process: the last line of your entrypoint script shou...
- Trap signals in the shell script if you must manage multiple processes:
- Use --init flag (docker run --init) to inject tini as PID 1, which properly forwards signals and ...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-105-docker-q99-after-a-container-has-been-running-for-several-days-you-want-to-see-exactly-what-files-were-added-modified-or-deleted-inside-the-container-compared-to-its-original-image-how-do-you-do-this-without-stopping-the-container-l2"></a>
### 105. Docker Q99: After a container has been running for several days you want to see exactly what files were added modified or deleted inside the container compared to its original image How do you do this without stopping the container [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Must enable BuildKit` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"After a container has been running for several days, you want to see exactly what files were added, modified, or deleted inside the container compared to its original image. How do you do this without stopping the container?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"During an image optimization initiative across our services, we solved this exact problem. The interviewer is testing: `docker diff`, container writable layer inspection.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Use `docker diff ` to inspect the container's writable layer against its base image:

- `A` — Added (file didn't exist in the image)
- `C` — Changed (file was modified)
- `D` — Deleted (file existed in image but was removed)

##### 2️⃣ Remediation & Permanent Safeguards

Output uses three markers: Example output: This is invaluable for debugging unexpected disk growth, verifying that containers aren't writing to unexpected locations, and auditing what a compromised container may have modified. Combine with `--read-only` root filesystem to prevent unexpected mutations in the first place. ---

```bash
docker diff my-running-container
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: A — Added (file didn't exist in the image).

#### ⏱️ 60-Second Elevator Pitch Summary

- A — Added (file didn't exist in the image)
- C — Changed (file was modified)
- D — Deleted (file existed in image but was removed)

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-106-docker-q100-you-have-two-containers-on-the-same-docker-network-container-a-needs-to-reach-container-b-but-container-bs-name-is-a-long-auto-generated-string-like-project-backend-service-1-you-want-a-shorter-more-memorable-hostname-how-do-you-assign-one-without-renaming-the-container-l2"></a>
### 106. Docker Q100: You have two containers on the same Docker network Container A needs to reach Container B but Container Bs name is a long auto-generated string like project_backend_service_1 You want a shorter more memorable hostname How do you assign one without renaming the container [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Production Scenario [L2]`

**Tags:** `Docker` `Must enable BuildKit` `L2` `Containers` `Linux`

> **Interview Question:**  
> *"You have two containers on the same Docker network. Container A needs to reach Container B, but Container B's name is a long auto-generated string like `project_backend_service_1`. You want a shorter, more memorable hostname. How do you assign one without renaming the container?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Container stability relies on clean signal handling (SIGTERM vs SIGKILL) and immutable image tagging. The interviewer is testing: Docker network aliases, DNS in user-defined networks.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use **network aliases** to assign additional DNS names to a container on a specific network: Now `myapp-frontend` can reach the backend using simply `backend` as the hostname, regardless of the actual container name. In Docker Compose, network aliases are configured under the `networks` key: Multiple aliases can be assigned, and multiple containers can share the same alias (Docker's embedded DNS round-robins between them — useful for simple load balancing). Aliases are scoped to the network, so the same alias can mean different things on different networks. --- *More Docker scenarios added periodically. PRs welcome.*

```bash
docker network create app-net
docker run -d --network app-net --network-alias backend myapp-backend
docker run -d --network app-net myapp-frontend
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use network aliases to assign additional DNS names to a container on a specific network:.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use network aliases to assign additional DNS names to a container on a specific network:
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-107-kubernetes-q1-your-pod-is-stuck-in-pending-state-what-do-you-do-l1"></a>
### 107. Kubernetes Q1: Your pod is stuck in Pending state What do you do [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Kubernetes` • `Troubleshooting & Debugging` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Kubernetes` `Troubleshooting & Debugging` `L1` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Your pod is stuck in `Pending` state. What do you do?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. The interviewer is testing: Basic Kubernetes debugging workflow.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

First run `kubectl describe pod ` and look at the **Events** section at the bottom. Common reasons for Pending:

- **No nodes with enough resources** — the node doesn't have enough CPU or memory. Check with `kubectl get nodes` and `kubectl describe node`.
- **No matching node selector or affinity** — the pod has a `nodeSelector` that doesn't match any node label.
- **Taints not tolerated** — the node has a taint the pod doesn't tolerate.

##### 2️⃣ Remediation & Permanent Safeguards

Fix based on the root cause shown in the events. ---

- **PVC not bound** — if the pod needs a volume, the PersistentVolumeClaim may be stuck.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: No nodes with enough resources — the node doesn't have enough CPU or memory. Check with kubectl get nodes and kubectl describe nod.

#### ⏱️ 60-Second Elevator Pitch Summary

- No nodes with enough resources — the node doesn't have enough CPU or memory. Check with kubectl g...
- No matching node selector or affinity — the pod has a nodeSelector that doesn't match any node la...
- Taints not tolerated — the node has a taint the pod doesn't tolerate.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-108-kubernetes-q2-a-pod-is-in-crashloopbackoff-how-do-you-debug-it-l1"></a>
### 108. Kubernetes Q2: A pod is in CrashLoopBackOff How do you debug it [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Kubernetes` • `Troubleshooting & Debugging` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Kubernetes` `Troubleshooting & Debugging` `L1` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"A pod is in `CrashLoopBackOff`. How do you debug it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. The interviewer is testing: Log investigation and restart behavior understanding.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

`CrashLoopBackOff` means the container starts, crashes, and Kubernetes keeps restarting it with increasing delay.

- `kubectl logs ` — read the logs. If the container already restarted, use `kubectl logs  --previous` to get logs from the last crashed instance.
- `kubectl describe pod ` — check exit codes. Exit code `1` = app error, `137` = OOM killed, `139` = segfault.
- If logs are empty, the container may be crashing before writing anything — check the image and entrypoint command.

##### 2️⃣ Remediation & Permanent Safeguards

Steps: Common causes: app error on startup, wrong config/env vars, missing secrets, OOM. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: kubectl logs  — read the logs. If the container already restarted, use kubectl logs  --previous to get logs from the last crashed .

#### ⏱️ 60-Second Elevator Pitch Summary

- kubectl logs  — read the logs. If the container already restarted, use kubectl logs  --previous t...
- kubectl describe pod  — check exit codes. Exit code 1 = app error, 137 = OOM killed, 139 = segfault.
- If logs are empty, the container may be crashing before writing anything — check the image and en...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-109-kubernetes-q3-a-pod-shows-oomkilled-in-its-status-what-happened-and-how-do-you-fix-it-l2"></a>
### 109. Kubernetes Q3: A pod shows OOMKilled in its status What happened and how do you fix it [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Troubleshooting & Debugging` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Troubleshooting & Debugging` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"A pod shows `OOMKilled` in its status. What happened and how do you fix it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. The interviewer is testing: Resource limits understanding.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

OOMKilled means the container exceeded its memory limit and the kernel killed it.

- Check current limits: `kubectl describe pod ` — look at the `Limits` section.
- Increase the memory limit in the deployment spec under `resources.limits.memory`.
- If you're unsure what the right value is, set a higher limit temporarily and monitor actual usage with `kubectl top pod `.

##### 2️⃣ Remediation & Permanent Safeguards

Fix: ---

- Long term: use VPA (Vertical Pod Autoscaler) to auto-tune resource requests and limits.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Check current limits: kubectl describe pod  — look at the Limits section..

#### ⏱️ 60-Second Elevator Pitch Summary

- Check current limits: kubectl describe pod  — look at the Limits section.
- Increase the memory limit in the deployment spec under resources.limits.memory.
- If you're unsure what the right value is, set a higher limit temporarily and monitor actual usage...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-110-kubernetes-q4-your-deployment-rollout-is-stuck-pods-from-the-new-version-arent-coming-up-but-old-ones-are-still-running-whats-happening-l2"></a>
### 110. Kubernetes Q4: Your deployment rollout is stuck Pods from the new version arent coming up but old ones are still running Whats happening [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Troubleshooting & Debugging` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Troubleshooting & Debugging` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Your deployment rollout is stuck. Pods from the new version aren't coming up but old ones are still running. What's happening?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. The interviewer is testing: RollingUpdate strategy and rollout debugging.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

This is typical RollingUpdate behavior when new pods fail healthchecks.

- Liveness or readiness probe failing in the new version.
- New image has a bug and is crashing.
- Resource limits hit — new pods can't schedule.

##### 2️⃣ Remediation & Permanent Safeguards

Check: `kubectl rollout status deployment/` — it will show if it's stuck. Then `kubectl describe pod ` to see why new pods aren't ready. Common causes: To rollback immediately: `kubectl rollout undo deployment/` To investigate without rolling back, describe the new failing pods and check logs. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Liveness or readiness probe failing in the new version..

#### ⏱️ 60-Second Elevator Pitch Summary

- Liveness or readiness probe failing in the new version.
- New image has a bug and is crashing.
- Resource limits hit — new pods can't schedule.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-111-kubernetes-q5-a-pod-is-running-but-your-app-is-not-reachable-via-the-service-what-do-you-check-l2"></a>
### 111. Kubernetes Q5: A pod is Running but your app is not reachable via the Service What do you check [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Troubleshooting & Debugging` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Troubleshooting & Debugging` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"A pod is `Running` but your app is not reachable via the Service. What do you check?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. The interviewer is testing: Service-to-pod connectivity debugging.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

---

- **Check pod labels vs service selector** — `kubectl describe service ` shows the selector. `kubectl get pod --show-labels` shows pod labels. They must match exactly.
- **Check endpoints** — `kubectl get endpoints `. If it shows ``, the selector doesn't match any pod.
- **Check if the pod is Ready** — even if Running, if the readiness probe fails, the pod is removed from endpoints.

##### 2️⃣ Remediation & Permanent Safeguards

Execute the resolution runbook and verify workload health:

- **Check the port mapping** — service `targetPort` must match the container's listening port.
- **Test from inside the cluster** — `kubectl exec -it  -- curl :` to isolate if it's a network policy or external routing issue.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Check pod labels vs service selector — kubectl describe service  shows the selector. kubectl get pod --show-labels shows pod label.

#### ⏱️ 60-Second Elevator Pitch Summary

- Check pod labels vs service selector — kubectl describe service  shows the selector. kubectl get ...
- Check endpoints — kubectl get endpoints . If it shows , the selector doesn't match any pod.
- Check if the pod is Ready — even if Running, if the readiness probe fails, the pod is removed fro...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-112-kubernetes-q6-a-node-in-your-cluster-shows-notready-your-team-is-panicking-because-several-services-are-on-it-whats-your-action-plan-l3"></a>
### 112. Kubernetes Q6: A node in your cluster shows NotReady Your team is panicking because several services are on it Whats your action plan [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Troubleshooting & Debugging` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Troubleshooting & Debugging` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"A node in your cluster shows `NotReady`. Your team is panicking because several services are on it. What's your action plan?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. The interviewer is testing: Incident response, node troubleshooting, pod eviction understanding.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

---

- **Don't panic — check if pods already rescheduled.** Kubernetes evicts pods from NotReady nodes after `pod-eviction-timeout` (default 5 min). Check `kubectl get pods -A -o wide | grep `.
- **Cordon the node** — `kubectl cordon ` prevents new pods from scheduling there while you investigate.
- **SSH into the node** and check:
- `systemctl status kubelet` — is kubelet running?
- `journalctl -u kubelet -n 100` — kubelet logs.

##### 2️⃣ Remediation & Permanent Safeguards

Execute the resolution runbook and verify workload health:

- Disk space: `df -h`. Full disk is a common cause.
- Memory: `free -m`.
- **Check the node's conditions**: `kubectl describe node ` — look for MemoryPressure, DiskPressure, PIDPressure.
- If unrecoverable, drain and delete: `kubectl drain  --ignore-daemonsets --delete-emptydir-data` then terminate the VM.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Don't panic — check if pods already rescheduled. Kubernetes evicts pods from NotReady nodes after pod-eviction-timeout (default 5 .

#### ⏱️ 60-Second Elevator Pitch Summary

- Don't panic — check if pods already rescheduled. Kubernetes evicts pods from NotReady nodes after...
- Cordon the node — kubectl cordon  prevents new pods from scheduling there while you investigate.
- SSH into the node and check:

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-113-kubernetes-q7-your-hpa-horizontal-pod-autoscaler-is-not-scaling-up-even-though-cpu-usage-is-high-why-l2"></a>
### 113. Kubernetes Q7: Your HPA (Horizontal Pod Autoscaler) is not scaling up even though CPU usage is high Why [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Troubleshooting & Debugging` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Troubleshooting & Debugging` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Your HPA (Horizontal Pod Autoscaler) is not scaling up even though CPU usage is high. Why?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. The interviewer is testing: HPA prerequisites and metrics-server dependency.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

HPA needs `metrics-server` to be installed and working. Without it, HPA can't read CPU/memory metrics and shows `` in `kubectl get hpa`.

- `kubectl get hpa` — if it shows `/50%` for current metric, metrics-server is missing or broken.
- `kubectl top pods` — if this fails, metrics-server is the problem.
- Also check that pods have **resource requests defined** — HPA calculates usage as a percentage of the request value. No requests = HPA can't calculate.

##### 2️⃣ Remediation & Permanent Safeguards

Check: Fix: Install metrics-server, set resource requests on pods. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: kubectl get hpa — if it shows /50% for current metric, metrics-server is missing or broken..

#### ⏱️ 60-Second Elevator Pitch Summary

- kubectl get hpa — if it shows /50% for current metric, metrics-server is missing or broken.
- kubectl top pods — if this fails, metrics-server is the problem.
- Also check that pods have resource requests defined — HPA calculates usage as a percentage of the...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-114-kubernetes-q8-a-pod-has-been-running-fine-for-weeks-and-suddenly-starts-failing-with-imagepullbackoff-nothing-in-the-pod-spec-changed-what-could-cause-this-l3"></a>
### 114. Kubernetes Q8: A pod has been running fine for weeks and suddenly starts failing with ImagePullBackOff Nothing in the pod spec changed What could cause this [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Troubleshooting & Debugging` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Troubleshooting & Debugging` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"A pod has been running fine for weeks and suddenly starts failing with `ImagePullBackOff`. Nothing in the pod spec changed. What could cause this?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. The interviewer is testing: Image registry auth and image availability awareness.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Since nothing changed in the spec, suspect external changes:

- **Registry credentials expired** — imagePullSecret token rotated or expired.
- **Image was deleted from the registry** — someone deleted the tag from Docker Hub or ECR.
- **Registry is down or unreachable** — network issue or registry outage.

##### 2️⃣ Remediation & Permanent Safeguards

Check: `kubectl describe pod ` — the event will say exactly which registry returned what error (401 Unauthorized, 404 Not Found, etc.). ---

- **Rate limiting** — Docker Hub has pull rate limits for unauthenticated/free accounts.
- **Private registry changed auth** — ECR tokens expire every 12 hours if not refreshed.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Registry credentials expired — imagePullSecret token rotated or expired..

#### ⏱️ 60-Second Elevator Pitch Summary

- Registry credentials expired — imagePullSecret token rotated or expired.
- Image was deleted from the registry — someone deleted the tag from Docker Hub or ECR.
- Registry is down or unreachable — network issue or registry outage.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-115-kubernetes-q9-you-run-kubectl-exec-it-pod-bash-and-get-container-not-found-whats-wrong-l2"></a>
### 115. Kubernetes Q9: You run kubectl exec -it <pod> -- bash and get container not found Whats wrong [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Troubleshooting & Debugging` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Troubleshooting & Debugging` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"You run `kubectl exec -it  -- bash` and get "container not found." What's wrong?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. The interviewer is testing: Multi-container pod awareness.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

If a pod has multiple containers, you need to specify which one: Get container names with: `kubectl get pod  -o jsonpath='{.spec.containers[*].name}'` Also — some minimal images (Alpine, distroless) don't have `bash`. Try `sh` instead. ---

```bash
kubectl exec -it <pod> -c <container-name> -- bash
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: If a pod has multiple containers, you need to specify which one:.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: If a pod has multiple containers, you need to specify which one:
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-116-kubernetes-q10-your-init-container-is-stuck-and-the-main-container-never-starts-how-do-you-debug-l2"></a>
### 116. Kubernetes Q10: Your init container is stuck and the main container never starts How do you debug [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Troubleshooting & Debugging` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Troubleshooting & Debugging` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Your init container is stuck and the main container never starts. How do you debug?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. The interviewer is testing: Init container execution order and logging.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Init containers run sequentially before the main container. If one fails, the pod stays in `Init:0/1` or similar state.

- `kubectl describe pod ` — check init container status.
- `kubectl logs  -c ` — get init container logs.
- Common causes: init container script fails (wrong path, missing file), waiting for a service that's not up (like a DB), permissions issue.

##### 2️⃣ Remediation & Permanent Safeguards

--- ## 🔵 Deployments & Workloads ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: kubectl describe pod  — check init container status..

#### ⏱️ 60-Second Elevator Pitch Summary

- kubectl describe pod  — check init container status.
- kubectl logs  -c  — get init container logs.
- Common causes: init container script fails (wrong path, missing file), waiting for a service that...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-117-kubernetes-q11-whats-the-difference-between-a-deployment-and-a-statefulset-when-would-you-use-each-l1"></a>
### 117. Kubernetes Q11: Whats the difference between a Deployment and a StatefulSet When would you use each [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Kubernetes` • `Deployments & Workloads` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Kubernetes` `Deployments & Workloads` `L1` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What's the difference between a Deployment and a StatefulSet? When would you use each?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

If your app needs to remember who it is (stable network ID, stable storage), use StatefulSet. Otherwise use Deployment.

- **Deployment** — for stateless apps. Pods are interchangeable. Any pod can handle any request. Use for web servers, APIs, workers.
- **StatefulSet** — for stateful apps. Each pod gets a stable hostname (pod-0, pod-1...) and its own persistent volume. Pods start and stop in order. Use for databases, Kafka, Elasticsearch, Zookeeper.

##### 2️⃣ Remediation & Permanent Safeguards

---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Deployment — for stateless apps. Pods are interchangeable. Any pod can handle any request. Use for web servers, APIs, workers..

#### ⏱️ 60-Second Elevator Pitch Summary

- Deployment — for stateless apps. Pods are interchangeable. Any pod can handle any request. Use fo...
- StatefulSet — for stateful apps. Each pod gets a stable hostname (pod-0, pod-1...) and its own pe...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-118-kubernetes-q12-you-need-to-run-a-database-in-kubernetes-someone-says-just-use-a-deployment-with-a-pvc-is-that-okay-l2"></a>
### 118. Kubernetes Q12: You need to run a database in Kubernetes Someone says just use a Deployment with a PVC Is that okay [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Deployments & Workloads` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Deployments & Workloads` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"You need to run a database in Kubernetes. Someone says just use a Deployment with a PVC. Is that okay?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. The interviewer is testing: StatefulSet necessity understanding.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Not ideal. A Deployment doesn't guarantee stable pod identity or ordered startup/shutdown, which matters for clustered databases (Postgres HA, MySQL replication, Cassandra). Also, if a Deployment has multiple replicas, all pods might try to bind the same PVC — which only one can do (unless using ReadWriteMany).

- Each replica gets its own PVC via `volumeClaimTemplates`.
- Pods get stable DNS names (e.g., `mysql-0.mysql`, `mysql-1.mysql`) needed for replication setup.
- Ordered startup ensures primary starts before replicas.

##### 2️⃣ Remediation & Permanent Safeguards

StatefulSet is the right choice because: For a single-instance DB with no replication, a Deployment + PVC works fine but is still a corner case. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Each replica gets its own PVC via volumeClaimTemplates..

#### ⏱️ 60-Second Elevator Pitch Summary

- Each replica gets its own PVC via volumeClaimTemplates.
- Pods get stable DNS names (e.g., mysql-0.mysql, mysql-1.mysql) needed for replication setup.
- Ordered startup ensures primary starts before replicas.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-119-kubernetes-q13-you-updated-a-configmap-thats-mounted-as-an-environment-variable-in-a-pod-the-pod-still-shows-the-old-value-why-l2"></a>
### 119. Kubernetes Q13: You updated a ConfigMap thats mounted as an environment variable in a pod The pod still shows the old value Why [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Deployments & Workloads` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Deployments & Workloads` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"You updated a ConfigMap that's mounted as an environment variable in a pod. The pod still shows the old value. Why?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Environment variables are loaded at pod start time. Changing a ConfigMap doesn't restart running pods, so they keep the old values. Fix: **Rolling restart** the deployment — `kubectl rollout restart deployment/`. This creates new pods that pick up the new ConfigMap values. Note: If the ConfigMap is mounted as a **volume file** (not env var), Kubernetes will eventually update the file in the running pod without restart (takes ~1 min). But env vars never auto-update. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Environment variables are loaded at pod start time. Changing a ConfigMap doesn't restart running pods, so they keep the old values.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Environment variables are loaded at pod start time. Changing a ConfigMap doesn't restart runnin
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-120-kubernetes-q14-how-would-you-ensure-a-critical-pod-always-runs-on-the-same-node-l2"></a>
### 120. Kubernetes Q14: How would you ensure a critical pod always runs on the same node [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Deployments & Workloads` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Deployments & Workloads` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How would you ensure a critical pod always runs on the same node?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Two approaches:

- **NodeSelector** — add a label to the node (`kubectl label node  type=critical`) and add `nodeSelector: {type: critical}` to the pod spec. Simple but inflexible.
- **Node Affinity** — more expressive, supports `requiredDuringSchedulingIgnoredDuringExecution` (hard rule) or `preferredDuringScheduling...` (soft preference).

##### 2️⃣ Remediation & Permanent Safeguards

For "always the same node" — use `requiredDuringSchedulingIgnoredDuringExecution` with `nodeAffinity`. But be careful: if that node goes down, the pod won't reschedule elsewhere. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: NodeSelector — add a label to the node (kubectl label node  type=critical) and add nodeSelector: {type: critical} to the pod spec..

#### ⏱️ 60-Second Elevator Pitch Summary

- NodeSelector — add a label to the node (kubectl label node  type=critical) and add nodeSelector: ...
- Node Affinity — more expressive, supports requiredDuringSchedulingIgnoredDuringExecution (hard ru...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-121-kubernetes-q15-you-want-to-make-sure-two-pods-of-the-same-app-never-run-on-the-same-node-how-l2"></a>
### 121. Kubernetes Q15: You want to make sure two pods of the same app NEVER run on the same node How [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Deployments & Workloads` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Deployments & Workloads` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"You want to make sure two pods of the same app NEVER run on the same node. How?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use **Pod Anti-Affinity**: `topologyKey: kubernetes.io/hostname` means "don't put two pods with label `app: myapp` on the same host." Use `required` for a hard rule or `preferred` to let Kubernetes still schedule if no option exists. ---

```bash
affinity:
  podAntiAffinity:
    requiredDuringSchedulingIgnoredDuringExecution:
    - labelSelector:
        matchLabels:
          app: myapp
      topologyKey: kubernetes.io/hostname
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use Pod Anti-Affinity:.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use Pod Anti-Affinity:
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-122-kubernetes-q16-your-deployment-has-10-replicas-you-need-to-do-a-zero-downtime-deploy-of-a-new-version-how-do-you-configure-and-verify-it-l3"></a>
### 122. Kubernetes Q16: Your deployment has 10 replicas You need to do a zero-downtime deploy of a new version How do you configure and verify it [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Deployments & Workloads` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Deployments & Workloads` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Your deployment has 10 replicas. You need to do a zero-downtime deploy of a new version. How do you configure and verify it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Configure RollingUpdate strategy:

- `kubectl rollout status deployment/` — watch it progress.
- Monitor your health endpoint / app metrics during rollout.
- If something goes wrong: `kubectl rollout undo deployment/`.

##### 2️⃣ Remediation & Permanent Safeguards

`maxUnavailable: 0` ensures old pods aren't removed until new ones pass readiness probes. Verify: Also make sure your **readiness probe is accurate** — this is the gating mechanism for zero-downtime. A bad probe that returns ready too early defeats the whole strategy. ---

```bash
strategy:
  type: RollingUpdate
  rollingUpdate:
    maxSurge: 2        # max extra pods during update
    maxUnavailable: 0  # never kill old pod before new one is ready
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: kubectl rollout status deployment/ — watch it progress..

#### ⏱️ 60-Second Elevator Pitch Summary

- kubectl rollout status deployment/ — watch it progress.
- Monitor your health endpoint / app metrics during rollout.
- If something goes wrong: kubectl rollout undo deployment/.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-123-kubernetes-q17-what-is-a-daemonset-and-when-do-you-use-it-l1"></a>
### 123. Kubernetes Q17: What is a DaemonSet and when do you use it [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Kubernetes` • `Deployments & Workloads` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Kubernetes` `Deployments & Workloads` `L1` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is a DaemonSet and when do you use it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

A DaemonSet ensures one pod runs on every node (or a subset of nodes). When a new node joins the cluster, the DaemonSet automatically places a pod on it.

- Log collectors (Fluentd, Filebeat) — need to run on every node to collect logs.
- Monitoring agents (Prometheus node-exporter) — need node-level metrics from every node.
- Network plugins (Calico, Weave) — need to run on every node.

##### 2️⃣ Remediation & Permanent Safeguards

Use cases: ---

- Security agents (Falco, Wazuh) — need to watch every node.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Log collectors (Fluentd, Filebeat) — need to run on every node to collect logs..

#### ⏱️ 60-Second Elevator Pitch Summary

- Log collectors (Fluentd, Filebeat) — need to run on every node to collect logs.
- Monitoring agents (Prometheus node-exporter) — need node-level metrics from every node.
- Network plugins (Calico, Weave) — need to run on every node.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-124-kubernetes-q18-you-have-a-daemonset-but-some-nodes-arent-getting-a-pod-why-l2"></a>
### 124. Kubernetes Q18: You have a DaemonSet but some nodes arent getting a pod Why [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Deployments & Workloads` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Deployments & Workloads` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"You have a DaemonSet but some nodes aren't getting a pod. Why?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Common reasons:

- **Node selector or affinity mismatch** — DaemonSet has a `nodeSelector` or affinity rule that doesn't match those nodes.
- **Node has a taint** — the DaemonSet pods don't have a matching toleration. Add the toleration to the DaemonSet spec.
- **Node is cordoned** — `kubectl cordon` prevents any new pod scheduling.

##### 2️⃣ Remediation & Permanent Safeguards

Check: `kubectl describe daemonset ` — look at the Selector and Tolerations. Compare with `kubectl describe node `. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Node selector or affinity mismatch — DaemonSet has a nodeSelector or affinity rule that doesn't match those nodes..

#### ⏱️ 60-Second Elevator Pitch Summary

- Node selector or affinity mismatch — DaemonSet has a nodeSelector or affinity rule that doesn't m...
- Node has a taint — the DaemonSet pods don't have a matching toleration. Add the toleration to the...
- Node is cordoned — kubectl cordon prevents any new pod scheduling.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-125-kubernetes-q19-when-would-you-use-a-job-vs-a-cronjob-l2"></a>
### 125. Kubernetes Q19: When would you use a Job vs a CronJob [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Deployments & Workloads` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Deployments & Workloads` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"When would you use a Job vs a CronJob?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

CronJob creates a new Job object on each schedule trigger. Both ensure the task runs to completion and can be configured to retry on failure.

- **Job** — run a task once to completion. E.g., database migration on deploy, one-time data processing, sending a batch of emails.
- **CronJob** — run a task on a schedule (like cron in Linux). E.g., nightly backups, hourly reports, weekly cleanup jobs.

##### 2️⃣ Remediation & Permanent Safeguards

---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Job — run a task once to completion. E.g., database migration on deploy, one-time data processing, sending a batch of emails..

#### ⏱️ 60-Second Elevator Pitch Summary

- Job — run a task once to completion. E.g., database migration on deploy, one-time data processing...
- CronJob — run a task on a schedule (like cron in Linux). E.g., nightly backups, hourly reports, w...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-126-kubernetes-q20-your-cronjob-is-creating-overlapping-runs-the-previous-job-hasnt-finished-when-the-next-one-starts-how-do-you-fix-it-l2"></a>
### 126. Kubernetes Q20: Your CronJob is creating overlapping runs — the previous job hasnt finished when the next one starts How do you fix it [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Deployments & Workloads` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Deployments & Workloads` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Your CronJob is creating overlapping runs — the previous job hasn't finished when the next one starts. How do you fix it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Set `concurrencyPolicy: Forbid` in the CronJob spec. This skips the new run if the previous one is still running.

- `Allow` (default) — multiple jobs can run at the same time.
- `Forbid` — skip the new run if old one still running.
- `Replace` — kill the old run and start a new one.

##### 2️⃣ Remediation & Permanent Safeguards

Options: Also check `startingDeadlineSeconds` — if a job is missed (e.g., cluster was down), Kubernetes may try to catch up on missed runs. --- ## 🟢 Networking ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Allow (default) — multiple jobs can run at the same time..

#### ⏱️ 60-Second Elevator Pitch Summary

- Allow (default) — multiple jobs can run at the same time.
- Forbid — skip the new run if old one still running.
- Replace — kill the old run and start a new one.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-127-kubernetes-q21-what-is-the-difference-between-clusterip-nodeport-and-loadbalancer-service-types-l1"></a>
### 127. Kubernetes Q21: What is the difference between ClusterIP NodePort and LoadBalancer service types [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Kubernetes` • `Networking` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Kubernetes` `Networking` `L1` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is the difference between ClusterIP, NodePort, and LoadBalancer service types?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

---

- **ClusterIP** — only accessible inside the cluster. Default type. Used for internal service-to-service communication.
- **NodePort** — opens a port (30000–32767) on every node. Traffic to `:` reaches the service. Used for dev/testing or when you manage your own load balancer.
- **LoadBalancer** — creates a cloud load balancer (AWS ELB, GCP LB) and assigns an external IP. Used in production to expose services to the internet. Only works in cloud environments.

##### 2️⃣ Remediation & Permanent Safeguards

Execute the resolution runbook and verify workload health:

#### 🎯 Key Architectural Takeaway
> Pro-Tip: ClusterIP — only accessible inside the cluster. Default type. Used for internal service-to-service communication..

#### ⏱️ 60-Second Elevator Pitch Summary

- ClusterIP — only accessible inside the cluster. Default type. Used for internal service-to-servic...
- NodePort — opens a port (30000–32767) on every node. Traffic to : reaches the service. Used for d...
- LoadBalancer — creates a cloud load balancer (AWS ELB, GCP LB) and assigns an external IP. Used i...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-128-kubernetes-q22-what-is-an-ingress-and-why-do-you-need-it-when-you-already-have-loadbalancer-services-l2"></a>
### 128. Kubernetes Q22: What is an Ingress and why do you need it when you already have LoadBalancer services [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Networking` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Networking` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is an Ingress and why do you need it when you already have LoadBalancer services?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Every LoadBalancer service creates a new cloud load balancer = new cost + new IP address. For 10 services, that's 10 load balancers.

- `api.myapp.com` → API service
- `app.myapp.com` → Frontend service
- `myapp.com/admin` → Admin service

##### 2️⃣ Remediation & Permanent Safeguards

Ingress uses **one** load balancer (the Ingress Controller) and routes HTTP/HTTPS traffic to different services based on hostname or URL path rules. Much cheaper and cleaner. Example: All through one load balancer. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: api.myapp.com → API service.

#### ⏱️ 60-Second Elevator Pitch Summary

- api.myapp.com → API service
- app.myapp.com → Frontend service
- myapp.com/admin → Admin service

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-129-kubernetes-q23-your-ingress-is-returning-404-for-a-path-that-youve-configured-what-do-you-check-l2"></a>
### 129. Kubernetes Q23: Your Ingress is returning 404 for a path that youve configured What do you check [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Networking` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Networking` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Your Ingress is returning 404 for a path that you've configured. What do you check?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

---

- **Check the Ingress resource** — `kubectl describe ingress ` — verify the path and service name are correct.
- **Check the IngressClass** — does the Ingress have the right `ingressClassName`? If multiple controllers exist (nginx, traefik), the wrong one might be handling it.
- **Check path type** — `Exact` vs `Prefix` vs `ImplementationSpecific`. `Exact` only matches `/api`, not `/api/users`. Use `Prefix` to match all subpaths.

##### 2️⃣ Remediation & Permanent Safeguards

Execute the resolution runbook and verify workload health:

- **Check backend service** — is the service name and port correct? Does the service have endpoints?
- **Ingress controller logs** — `kubectl logs -n ingress-nginx ` — nginx logs will show 404 details.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Check the Ingress resource — kubectl describe ingress  — verify the path and service name are correct..

#### ⏱️ 60-Second Elevator Pitch Summary

- Check the Ingress resource — kubectl describe ingress  — verify the path and service name are cor...
- Check the IngressClass — does the Ingress have the right ingressClassName? If multiple controller...
- Check path type — Exact vs Prefix vs ImplementationSpecific. Exact only matches /api, not /api/us...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-130-kubernetes-q24-you-have-a-microservices-app-where-service-a-should-never-talk-directly-to-service-c-only-through-service-b-how-do-you-enforce-this-in-kubernetes-l3"></a>
### 130. Kubernetes Q24: You have a microservices app where Service A should never talk directly to Service C only through Service B How do you enforce this in Kubernetes [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Networking` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Networking` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"You have a microservices app where Service A should never talk directly to Service C, only through Service B. How do you enforce this in Kubernetes?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use **NetworkPolicy**. By default, all pods can talk to all other pods. NetworkPolicy lets you restrict this. Example — block direct traffic to Service C except from Service B: This says: "Only accept incoming traffic to pods labeled `app: service-c` if it comes from pods labeled `app: service-b`." Note: NetworkPolicy requires a CNI plugin that supports it (Calico, Cilium, Weave). Flannel does not support NetworkPolicy by default. ---

```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: allow-only-from-b
spec:
  podSelector:
    matchLabels:
      app: service-c
  ingress:
  - from:
    - podSelector:
        matchLabels:
          app: service-b
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use NetworkPolicy. By default, all pods can talk to all other pods. NetworkPolicy lets you restrict this..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use NetworkPolicy. By default, all pods can talk to all other pods. NetworkPolicy lets you rest
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-131-kubernetes-q25-what-is-a-headless-service-and-why-would-you-use-it-l2"></a>
### 131. Kubernetes Q25: What is a headless service and why would you use it [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Networking` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Networking` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is a headless service and why would you use it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

A headless service has `clusterIP: None`. Instead of a single virtual IP, DNS queries for a headless service return the actual pod IPs directly.

- **StatefulSets** — each pod needs its own DNS name (`pod-0.service`, `pod-1.service`) for inter-pod communication (like database replication).
- **Client-side load balancing** — let the app choose which pod to connect to instead of going through kube-proxy.
- **Service discovery** — let your app discover all pod IPs directly.

##### 2️⃣ Remediation & Permanent Safeguards

Use cases: ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: StatefulSets — each pod needs its own DNS name (pod-0.service, pod-1.service) for inter-pod communication (like database replicati.

#### ⏱️ 60-Second Elevator Pitch Summary

- StatefulSets — each pod needs its own DNS name (pod-0.service, pod-1.service) for inter-pod commu...
- Client-side load balancing — let the app choose which pod to connect to instead of going through ...
- Service discovery — let your app discover all pod IPs directly.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-132-kubernetes-q26-a-request-is-going-from-pod-a-to-pod-b-via-a-service-and-its-very-slow-how-do-you-troubleshoot-network-latency-in-kubernetes-l3"></a>
### 132. Kubernetes Q26: A request is going from Pod A to Pod B via a Service and its very slow How do you troubleshoot network latency in Kubernetes [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Networking` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Networking` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"A request is going from Pod A to Pod B via a Service and it's very slow. How do you troubleshoot network latency in Kubernetes?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

---

- **Baseline test** — `kubectl exec -it  -- curl -o /dev/null -s -w "%{time_total}" http://:` to measure actual latency.
- **Bypass the service** — test pod-to-pod directly using the pod IP to see if latency is in kube-proxy/iptables: `kubectl exec -it  -- curl http://:`.
- **Check kube-proxy mode** — iptables vs ipvs. ipvs is faster at scale.
- **Check CNI** — network plugin issues. Run `ping` between pods to test raw network latency.

##### 2️⃣ Remediation & Permanent Safeguards

Execute the resolution runbook and verify workload health:

- **DNS latency** — `kubectl exec -it  -- time nslookup ` — DNS lookups through CoreDNS add latency. Consider `ndots:5` setting impact.
- **Node-level network** — check if nodes are on the same AZ. Cross-AZ traffic adds ~1-2ms.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Baseline test — kubectl exec -it  -- curl -o /dev/null -s -w "%{time_total}" http://: to measure actual latency..

#### ⏱️ 60-Second Elevator Pitch Summary

- Baseline test — kubectl exec -it  -- curl -o /dev/null -s -w "%{time_total}" http://: to measure ...
- Bypass the service — test pod-to-pod directly using the pod IP to see if latency is in kube-proxy...
- Check kube-proxy mode — iptables vs ipvs. ipvs is faster at scale.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-133-kubernetes-q27-dns-resolution-is-failing-inside-your-cluster-pods-cant-resolve-service-names-what-do-you-check-l2"></a>
### 133. Kubernetes Q27: DNS resolution is failing inside your cluster Pods cant resolve service names What do you check [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Networking` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Networking` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"DNS resolution is failing inside your cluster. Pods can't resolve service names. What do you check?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

---

- `kubectl get pods -n kube-system | grep coredns` — is CoreDNS running?
- `kubectl logs -n kube-system ` — any errors?
- Test DNS from inside a pod: `kubectl exec -it  -- nslookup kubernetes.default` — this should always resolve.

##### 2️⃣ Remediation & Permanent Safeguards

## 🟡 Storage ---

- Check `resolv.conf` inside the pod: `kubectl exec -it  -- cat /etc/resolv.conf` — should point to the cluster DNS IP.
- Check CoreDNS ConfigMap: `kubectl get configmap coredns -n kube-system -o yaml` — misconfigured forwarders can break external DNS resolution.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: kubectl get pods -n kube-system | grep coredns — is CoreDNS running?.

#### ⏱️ 60-Second Elevator Pitch Summary

- kubectl get pods -n kube-system | grep coredns — is CoreDNS running?
- kubectl logs -n kube-system  — any errors?
- Test DNS from inside a pod: kubectl exec -it  -- nslookup kubernetes.default — this should always...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-134-kubernetes-q28-what-is-the-difference-between-a-persistentvolume-pv-and-a-persistentvolumeclaim-pvc-l1"></a>
### 134. Kubernetes Q28: What is the difference between a PersistentVolume (PV) and a PersistentVolumeClaim (PVC) [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Kubernetes` • `Storage` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Kubernetes` `Storage` `L1` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is the difference between a PersistentVolume (PV) and a PersistentVolumeClaim (PVC)?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Think of PV as the actual parking spot and PVC as the parking ticket that reserves it.

- **PV (PersistentVolume)** — the actual storage resource. Could be an AWS EBS volume, NFS share, local disk. Created by a cluster admin or dynamically provisioned.
- **PVC (PersistentVolumeClaim)** — a request for storage by a pod. The pod says "I need 10GB of ReadWriteOnce storage" — the PVC finds a matching PV and binds to it.

##### 2️⃣ Remediation & Permanent Safeguards

---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: PV (PersistentVolume) — the actual storage resource. Could be an AWS EBS volume, NFS share, local disk. Created by a cluster admin.

#### ⏱️ 60-Second Elevator Pitch Summary

- PV (PersistentVolume) — the actual storage resource. Could be an AWS EBS volume, NFS share, local...
- PVC (PersistentVolumeClaim) — a request for storage by a pod. The pod says "I need 10GB of ReadWr...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-135-kubernetes-q29-a-pvc-is-stuck-in-pending-state-what-do-you-check-l2"></a>
### 135. Kubernetes Q29: A PVC is stuck in Pending state What do you check [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Storage` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Storage` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"A PVC is stuck in `Pending` state. What do you check?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

---

- **No matching PV** — check if a PV exists with matching `storageClassName`, `accessMode`, and enough capacity: `kubectl get pv`.
- **StorageClass doesn't exist** — `kubectl get storageclass`. If the PVC references a storage class that doesn't exist, it stays Pending.
- **Dynamic provisioner not working** — if using dynamic provisioning (like AWS EBS CSI driver), check if the CSI driver pods are running: `kubectl get pods -n kube-system | grep csi`.

##### 2️⃣ Remediation & Permanent Safeguards

Execute the resolution runbook and verify workload health:

- **Volume binding mode** — if the StorageClass has `volumeBindingMode: WaitForFirstConsumer`, the PVC stays Pending until a pod that uses it is scheduled. That's normal behavior.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: No matching PV — check if a PV exists with matching storageClassName, accessMode, and enough capacity: kubectl get pv..

#### ⏱️ 60-Second Elevator Pitch Summary

- No matching PV — check if a PV exists with matching storageClassName, accessMode, and enough capa...
- StorageClass doesn't exist — kubectl get storageclass. If the PVC references a storage class that...
- Dynamic provisioner not working — if using dynamic provisioning (like AWS EBS CSI driver), check ...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-136-kubernetes-q30-you-deleted-a-pvc-but-the-data-is-gone-how-could-you-have-protected-it-l2"></a>
### 136. Kubernetes Q30: You deleted a PVC but the data is gone How could you have protected it [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Storage` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Storage` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"You deleted a PVC but the data is gone. How could you have protected it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

By setting the **Reclaim Policy** on the PV or StorageClass:

- `Delete` (default for dynamic provisioning) — deletes the underlying volume when PVC is deleted. Data is gone.
- `Retain` — PV stays after PVC deletion. Data is preserved. Admin must manually reclaim.
- `Recycle` — deprecated, performed basic cleanup.

##### 2️⃣ Remediation & Permanent Safeguards

Also: use **VolumeSnapshot** to take backups before deleting. Or enable backup tools like Velero that snapshot PVC data. Lesson: Always check the StorageClass reclaim policy in production. Default `Delete` on cloud providers will wipe your data. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Delete (default for dynamic provisioning) — deletes the underlying volume when PVC is deleted. Data is gone..

#### ⏱️ 60-Second Elevator Pitch Summary

- Delete (default for dynamic provisioning) — deletes the underlying volume when PVC is deleted. Da...
- Retain — PV stays after PVC deletion. Data is preserved. Admin must manually reclaim.
- Recycle — deprecated, performed basic cleanup.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-137-kubernetes-q31-a-statefulset-pod-cant-start-because-its-trying-to-attach-a-volume-thats-still-attached-to-a-terminated-pod-on-a-dead-node-how-do-you-fix-it-l3"></a>
### 137. Kubernetes Q31: A StatefulSet pod cant start because its trying to attach a volume thats still attached to a terminated pod on a dead node How do you fix it [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Storage` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Storage` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"A StatefulSet pod can't start because it's trying to attach a volume that's still attached to a terminated pod on a dead node. How do you fix it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

This is a common scenario when a node dies without gracefully releasing its volumes. The PV shows `Terminating` or the pod shows volume attach error.

- Force delete the stuck pod: `kubectl delete pod  --grace-period=0 --force`
- Check if the PV is stuck: `kubectl describe pv ` — look for the node it's attached to.
- On AWS (EBS): use AWS CLI to force detach the volume: `aws ec2 detach-volume --volume-id  --force`

##### 2️⃣ Remediation & Permanent Safeguards

Steps: --- ## 🟣 RBAC & Security ---

- Check the VolumeAttachment object: `kubectl get volumeattachment` — delete the stuck one.
- The new pod should then attach the volume successfully.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Force delete the stuck pod: kubectl delete pod  --grace-period=0 --force.

#### ⏱️ 60-Second Elevator Pitch Summary

- Force delete the stuck pod: kubectl delete pod  --grace-period=0 --force
- Check if the PV is stuck: kubectl describe pv  — look for the node it's attached to.
- On AWS (EBS): use AWS CLI to force detach the volume: aws ec2 detach-volume --volume-id  --force

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-138-kubernetes-q32-a-developer-says-they-cant-list-pods-in-the-production-namespace-but-they-can-in-staging-how-do-you-debug-this-l2"></a>
### 138. Kubernetes Q32: A developer says they cant list pods in the production namespace but they can in staging How do you debug this [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `RBAC & Security` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `RBAC & Security` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"A developer says they can't list pods in the `production` namespace but they can in `staging`. How do you debug this?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

RBAC controls are namespace-scoped. Check:

- `kubectl auth can-i list pods --namespace=production --as=` — quick check.
- `kubectl get rolebinding -n production` — see what roles are bound in the production namespace.
- `kubectl get clusterrolebinding | grep ` — check if there's a cluster-level binding.

##### 2️⃣ Remediation & Permanent Safeguards

Fix: Create a RoleBinding in the `production` namespace giving the user the `view` or appropriate role: ---

```bash
kubectl create rolebinding dev-view --clusterrole=view --user=<username> -n production
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: kubectl auth can-i list pods --namespace=production --as= — quick check..

#### ⏱️ 60-Second Elevator Pitch Summary

- kubectl auth can-i list pods --namespace=production --as= — quick check.
- kubectl get rolebinding -n production — see what roles are bound in the production namespace.
- kubectl get clusterrolebinding | grep  — check if there's a cluster-level binding.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-139-kubernetes-q33-you-run-a-pod-that-needs-to-call-the-kubernetes-api-eg-to-list-other-pods-how-do-you-set-this-up-securely-l2"></a>
### 139. Kubernetes Q33: You run a pod that needs to call the Kubernetes API (eg to list other pods) How do you set this up securely [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `RBAC & Security` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `RBAC & Security` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"You run a pod that needs to call the Kubernetes API (e.g., to list other pods). How do you set this up securely?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

The pod will then have a token mounted at `/var/run/secrets/kubernetes.io/serviceaccount/token` which it can use to authenticate to the API server.

- Create a **ServiceAccount**: `kubectl create serviceaccount my-app -n my-namespace`
- Create a **Role** with only the needed permissions (principle of least privilege):
- Create a **RoleBinding** linking the ServiceAccount to the Role.

##### 2️⃣ Remediation & Permanent Safeguards

Avoid using the default ServiceAccount — it often has more permissions than needed. ---

- Set `serviceAccountName: my-app` in the pod spec.

```bash
rules:
- apiGroups: [""]
  resources: ["pods"]
  verbs: ["get", "list"]
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Create a ServiceAccount: kubectl create serviceaccount my-app -n my-namespace.

#### ⏱️ 60-Second Elevator Pitch Summary

- Create a ServiceAccount: kubectl create serviceaccount my-app -n my-namespace
- Create a Role with only the needed permissions (principle of least privilege):
- Create a RoleBinding linking the ServiceAccount to the Role.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-140-kubernetes-q34-someone-accidentally-ran-kubectl-delete-clusterrolebinding-cluster-admin-and-deleted-the-cluster-admin-binding-now-no-one-can-manage-the-cluster-what-do-you-do-l3"></a>
### 140. Kubernetes Q34: Someone accidentally ran kubectl delete clusterrolebinding cluster-admin and deleted the cluster admin binding Now no one can manage the cluster What do you do [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `RBAC & Security` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `RBAC & Security` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Someone accidentally ran `kubectl delete clusterrolebinding cluster-admin` and deleted the cluster admin binding. Now no one can manage the cluster. What do you do?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

This is a serious situation. If you're locked out of the API server entirely:

- **SSH directly to a control plane node**.
- Use `kubectl` with the admin kubeconfig at `/etc/kubernetes/admin.conf` (set `KUBECONFIG=/etc/kubernetes/admin.conf`). This uses certificate-based auth that bypasses RBAC.
- Recreate the cluster-admin binding:

##### 2️⃣ Remediation & Permanent Safeguards

Prevention: Never give a single ClusterRoleBinding a name that might be confused with a default. Back up RBAC configs. Use `--dry-run=client` before destructive commands. --- ## 🔵 Scaling & Performance ---

```bash
kubectl create clusterrolebinding cluster-admin \
  --clusterrole=cluster-admin \
  --user=<your-user>
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: SSH directly to a control plane node..

#### ⏱️ 60-Second Elevator Pitch Summary

- SSH directly to a control plane node.
- Use kubectl with the admin kubeconfig at /etc/kubernetes/admin.conf (set KUBECONFIG=/etc/kubernet...
- Recreate the cluster-admin binding:

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-141-kubernetes-q35-your-app-gets-a-traffic-spike-every-day-at-9-am-when-offices-open-hpa-isnt-fast-enough-what-do-you-do-l2"></a>
### 141. Kubernetes Q35: Your app gets a traffic spike every day at 9 AM when offices open HPA isnt fast enough What do you do [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Scaling & Performance` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Scaling & Performance` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Your app gets a traffic spike every day at 9 AM when offices open. HPA isn't fast enough. What do you do?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

HPA is reactive — it waits for metrics to breach thresholds before scaling. By then you've already had a slowdown.

- **Predictive scaling with KEDA** — KEDA supports cron-based scaling. Scale up at 8:45 AM before the spike hits.
- **VPA + HPA combo** — pre-tune pod sizes so each pod handles more load.
- **Keep minimum replicas higher** — set HPA `minReplicas` higher during business hours using a CronJob that patches the HPA.

##### 2️⃣ Remediation & Permanent Safeguards

Solutions: ---

- **Cluster Autoscaler tuning** — pre-warm nodes so pod scheduling isn't delayed when HPA does fire.
- **Horizontal + Cache** — add caching (Redis) to reduce per-request load.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Predictive scaling with KEDA — KEDA supports cron-based scaling. Scale up at 8:45 AM before the spike hits..

#### ⏱️ 60-Second Elevator Pitch Summary

- Predictive scaling with KEDA — KEDA supports cron-based scaling. Scale up at 8:45 AM before the s...
- VPA + HPA combo — pre-tune pod sizes so each pod handles more load.
- Keep minimum replicas higher — set HPA minReplicas higher during business hours using a CronJob t...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-142-kubernetes-q36-hpa-is-scaling-pods-up-and-down-too-aggressively-causing-instability-how-do-you-fix-it-l2"></a>
### 142. Kubernetes Q36: HPA is scaling pods up and down too aggressively causing instability How do you fix it [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Scaling & Performance` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Scaling & Performance` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"HPA is scaling pods up and down too aggressively, causing instability. How do you fix it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

HPA has a stabilization window to prevent thrashing. Tune it: Scale up fast, scale down slow — this is the recommended pattern to handle spiky traffic without instability. ---

```bash
behavior:
  scaleDown:
    stabilizationWindowSeconds: 300  # wait 5 min before scaling down
    policies:
    - type: Pods
      value: 1
      periodSeconds: 60  # scale down max 1 pod per minute
  scaleUp:
    stabilizationWindowSeconds: 0
    policies:
    - type: Pods
      value: 4
      periodSeconds: 60
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: HPA has a stabilization window to prevent thrashing. Tune it:.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: HPA has a stabilization window to prevent thrashing. Tune it:
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-143-kubernetes-q37-your-cluster-has-50-nodes-and-pod-scheduling-is-taking-10-seconds-what-could-cause-this-and-how-do-you-fix-it-l3"></a>
### 143. Kubernetes Q37: Your cluster has 50 nodes and pod scheduling is taking 10+ seconds What could cause this and how do you fix it [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Scaling & Performance` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Scaling & Performance` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Your cluster has 50 nodes and pod scheduling is taking 10+ seconds. What could cause this and how do you fix it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

The kube-scheduler evaluates all nodes for each pod. At 50 nodes it shouldn't be slow unless:

- **High pod churn** — many pods being created/deleted rapidly, overwhelming the scheduler queue.
- **Complex affinity rules** — complex pod/node affinity is O(n) per scheduling cycle.
- **Scheduler config `percentageOfNodesToScore`** — default is 100% for small clusters but can be lowered for large ones.

##### 2️⃣ Remediation & Permanent Safeguards

Fix: Profile with scheduler metrics, simplify affinity rules, tune `percentageOfNodesToScore`, optimize admission webhooks. --- ## 🟠 Advanced Scenarios ---

- **etcd latency** — scheduler reads from etcd. If etcd is slow, scheduling slows.
- **Webhook admission controllers** — mutating or validating webhooks add latency per-pod.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: High pod churn — many pods being created/deleted rapidly, overwhelming the scheduler queue..

#### ⏱️ 60-Second Elevator Pitch Summary

- High pod churn — many pods being created/deleted rapidly, overwhelming the scheduler queue.
- Complex affinity rules — complex pod/node affinity is O(n) per scheduling cycle.
- Scheduler config percentageOfNodesToScore — default is 100% for small clusters but can be lowered...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-144-kubernetes-q38-you-need-to-run-a-privileged-pod-that-can-modify-kernel-parameters-on-the-host-how-do-you-do-this-and-what-are-the-security-implications-l3"></a>
### 144. Kubernetes Q38: You need to run a privileged pod that can modify kernel parameters on the host How do you do this and what are the security implications [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"You need to run a privileged pod that can modify kernel parameters on the host. How do you do this and what are the security implications?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Set `securityContext` on the pod/container:

- A privileged container can escape to the host — it's essentially root on the node.
- If the app is compromised, the attacker owns the node.
- Never run privileged in production unless absolutely necessary (CNI plugins, node debuggers).

##### 2️⃣ Remediation & Permanent Safeguards

Or use specific capabilities instead of full privileged mode (much safer): Security implications: ---

- Use PSA (Pod Security Admission) or OPA/Gatekeeper to block privileged pods cluster-wide unless explicitly exempted.

```bash
securityContext:
  privileged: true
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: A privileged container can escape to the host — it's essentially root on the node..

#### ⏱️ 60-Second Elevator Pitch Summary

- A privileged container can escape to the host — it's essentially root on the node.
- If the app is compromised, the attacker owns the node.
- Never run privileged in production unless absolutely necessary (CNI plugins, node debuggers).

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-145-kubernetes-q39-you-need-to-do-a-zero-downtime-migration-of-a-statefulset-eg-upgrading-postgres-version-walk-me-through-your-approach-l3"></a>
### 145. Kubernetes Q39: You need to do a zero-downtime migration of a StatefulSet (eg upgrading Postgres version) Walk me through your approach [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"You need to do a zero-downtime migration of a StatefulSet (e.g., upgrading Postgres version). Walk me through your approach."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

StatefulSets don't support zero-downtime rolling updates as cleanly as Deployments because each pod has unique state.

- **Take a backup first** — always. Snapshot the PVC with VolumeSnapshot or pg_dump.
- **Set `updateStrategy` to `OnDelete`** — this lets you control which pods update manually.
- **Update the StatefulSet spec** (new image version).
- **Delete pods one at a time** — start with replicas (highest ordinal), not the primary. Let each pod restart with the new version and come up healthy before proceeding.

##### 2️⃣ Remediation & Permanent Safeguards

Approach: For major Postgres version upgrades: consider blue-green approach — spin up new StatefulSet, replicate data, cut traffic over. ---

- **Verify replication health** between each pod update.
- **Update the primary last** — failover to a replica first if needed.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Take a backup first — always. Snapshot the PVC with VolumeSnapshot or pg_dump..

#### ⏱️ 60-Second Elevator Pitch Summary

- Take a backup first — always. Snapshot the PVC with VolumeSnapshot or pg_dump.
- Set updateStrategy to OnDelete — this lets you control which pods update manually.
- Update the StatefulSet spec (new image version).

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-146-kubernetes-q40-your-team-wants-to-implement-gitops-for-kubernetes-what-tools-would-you-recommend-and-what-does-the-workflow-look-like-l3"></a>
### 146. Kubernetes Q40: Your team wants to implement GitOps for Kubernetes What tools would you recommend and what does the workflow look like [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Your team wants to implement GitOps for Kubernetes. What tools would you recommend and what does the workflow look like?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Tools: **ArgoCD** or **Flux** — both are CNCF projects.

- Developer pushes code → CI pipeline builds image, pushes to registry, updates the image tag in the Git repo (Helm values or kustomize overlay).
- ArgoCD/Flux watches the Git repo. Detects the change.
- ArgoCD/Flux applies the new manifests to the cluster.
- If the cluster state drifts from Git (someone does `kubectl apply` manually), ArgoCD marks the app as OutOfSync and can auto-correct.
- Git is the single source of truth.

##### 2️⃣ Remediation & Permanent Safeguards

GitOps workflow: Benefits: ---

- All changes are auditable (git log = change history).
- Rollback = `git revert`.
- No kubectl access needed for developers in production.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Developer pushes code → CI pipeline builds image, pushes to registry, updates the image tag in the Git repo (Helm values or kustom.

#### ⏱️ 60-Second Elevator Pitch Summary

- Developer pushes code → CI pipeline builds image, pushes to registry, updates the image tag in th...
- ArgoCD/Flux watches the Git repo. Detects the change.
- ArgoCD/Flux applies the new manifests to the cluster.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-147-kubernetes-q41-how-do-you-handle-secrets-in-kubernetes-what-are-the-problems-with-default-kubernetes-secrets-l2"></a>
### 147. Kubernetes Q41: How do you handle secrets in Kubernetes What are the problems with default Kubernetes Secrets [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you handle secrets in Kubernetes? What are the problems with default Kubernetes Secrets?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Default Kubernetes Secrets problems:

- They're only base64 encoded, not encrypted. Anyone with etcd access can read them.
- They're stored in etcd in plaintext by default (unless etcd encryption is enabled).
- RBAC can restrict who reads them, but it's easy to accidentally over-grant.
- **Encrypt etcd at rest** — enable `EncryptionConfiguration` in the API server.

##### 2️⃣ Remediation & Permanent Safeguards

Better approaches: Production recommendation: External Secrets Operator + AWS Secrets Manager or HashiCorp Vault. ---

- **External secrets** — use **External Secrets Operator** to sync secrets from AWS Secrets Manager, HashiCorp Vault, or GCP Secret Manager into Kubernetes Secrets.
- **Vault Agent Injector** — inject secrets directly into pods as files without storing in etcd at all.
- **Sealed Secrets (Bitnami)** — encrypt secrets before storing in Git. Safe to commit.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: They're only base64 encoded, not encrypted. Anyone with etcd access can read them..

#### ⏱️ 60-Second Elevator Pitch Summary

- They're only base64 encoded, not encrypted. Anyone with etcd access can read them.
- They're stored in etcd in plaintext by default (unless etcd encryption is enabled).
- RBAC can restrict who reads them, but it's easy to accidentally over-grant.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-148-kubernetes-q42-a-developer-wants-to-test-a-microservice-that-depends-on-8-other-services-setting-up-the-full-cluster-locally-is-impractical-what-would-you-suggest-l3"></a>
### 148. Kubernetes Q42: A developer wants to test a microservice that depends on 8 other services Setting up the full cluster locally is impractical What would you suggest [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"A developer wants to test a microservice that depends on 8 other services. Setting up the full cluster locally is impractical. What would you suggest?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Several approaches:

- **Telepresence** — run the developer's service locally but connected to the real cluster. Traffic from/to the real cluster routes through the local process. Feels like running in-cluster.
- **Skaffold** — automates build-deploy cycles. Code change → auto-build → auto-deploy to dev namespace. Fast inner loop.
- **Namespace-based isolation** — give the developer their own namespace with all dependencies deployed but pointing to shared/mocked backends.

##### 2️⃣ Remediation & Permanent Safeguards

Best combo: Telepresence + a shared dev cluster where real dependent services run. ---

- **Service virtualization** — mock the dependencies the developer doesn't care about using tools like WireMock or Microcks.
- **KinD or k3d** — lightweight local Kubernetes for running the full stack locally if resources allow.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Telepresence — run the developer's service locally but connected to the real cluster. Traffic from/to the real cluster routes thro.

#### ⏱️ 60-Second Elevator Pitch Summary

- Telepresence — run the developer's service locally but connected to the real cluster. Traffic fro...
- Skaffold — automates build-deploy cycles. Code change → auto-build → auto-deploy to dev namespace...
- Namespace-based isolation — give the developer their own namespace with all dependencies deployed...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-149-kubernetes-q43-your-cluster-upgrade-from-126-to-127-failed-halfway-through-control-plane-is-on-127-but-worker-nodes-are-still-on-126-is-this-okay-l2"></a>
### 149. Kubernetes Q43: Your cluster upgrade from 126 to 127 failed halfway through Control plane is on 127 but worker nodes are still on 126 Is this okay [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Your cluster upgrade from 1.26 to 1.27 failed halfway through. Control plane is on 1.27 but worker nodes are still on 1.26. Is this okay?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Yes — this is a supported temporary state during upgrades. Kubernetes supports **N-2 version skew** between control plane and nodes. A 1.27 control plane can manage 1.25, 1.26, and 1.27 nodes.

- Verify the control plane is healthy: `kubectl get nodes` — control plane nodes should show 1.27.
- Continue upgrading worker nodes one by one: drain, upgrade kubelet/kubectl/kubeadm, uncordon.
- Do not skip more than one minor version during upgrades.

##### 2️⃣ Remediation & Permanent Safeguards

Next steps: Never upgrade worker nodes before the control plane — that would be an unsupported configuration. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Verify the control plane is healthy: kubectl get nodes — control plane nodes should show 1.27..

#### ⏱️ 60-Second Elevator Pitch Summary

- Verify the control plane is healthy: kubectl get nodes — control plane nodes should show 1.27.
- Continue upgrading worker nodes one by one: drain, upgrade kubelet/kubectl/kubeadm, uncordon.
- Do not skip more than one minor version during upgrades.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-150-kubernetes-q44-how-do-you-handle-configuration-that-differs-between-environments-dev-staging-prod-in-kubernetes-l2"></a>
### 150. Kubernetes Q44: How do you handle configuration that differs between environments (dev staging prod) in Kubernetes [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you handle configuration that differs between environments (dev, staging, prod) in Kubernetes?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Two main approaches:

- **Kustomize** — base manifests + environment-specific overlays. Overlay patches change values (image tags, resource limits, replica counts) per environment without duplicating YAML.
- **Helm** — use different `values.yaml` files per environment. `helm install -f values.prod.yaml` applies prod-specific values.
- Use same manifests for all environments (promotes "production parity").

##### 2️⃣ Remediation & Permanent Safeguards

Best practice: ---

- Only override what genuinely differs: image tags, replica counts, resource limits, ingress hostnames, secret references.
- Don't use separate Deployment files per environment — too much duplication and drift.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Kustomize — base manifests + environment-specific overlays. Overlay patches change values (image tags, resource limits, replica co.

#### ⏱️ 60-Second Elevator Pitch Summary

- Kustomize — base manifests + environment-specific overlays. Overlay patches change values (image ...
- Helm — use different values.yaml files per environment. helm install -f values.prod.yaml applies ...
- Use same manifests for all environments (promotes "production parity").

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-151-kubernetes-q45-you-want-to-implement-pod-disruption-budgets-across-your-cluster-what-is-a-pdb-and-how-does-it-protect-your-services-l3"></a>
### 151. Kubernetes Q45: You want to implement pod disruption budgets across your cluster What is a PDB and how does it protect your services [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"You want to implement pod disruption budgets across your cluster. What is a PDB and how does it protect your services?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

A **PodDisruptionBudget (PDB)** limits how many pods of a deployment can be voluntarily disrupted at the same time. "Voluntary disruption" includes node drains, rolling updates, and cluster upgrades.

- `minAvailable: 2` — at least 2 pods must remain.
- `maxUnavailable: 1` — at most 1 pod can be down at a time.

##### 2️⃣ Remediation & Permanent Safeguards

Example: This says: "When draining a node, don't proceed if it would bring my-app below 2 running pods." Use: During a cluster upgrade when nodes are drained, without PDBs your entire deployment could go down if all pods happen to be on the nodes being drained. ---

```yaml
apiVersion: policy/v1
kind: PodDisruptionBudget
metadata:
  name: my-app-pdb
spec:
  minAvailable: 2
  selector:
    matchLabels:
      app: my-app
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: minAvailable: 2 — at least 2 pods must remain..

#### ⏱️ 60-Second Elevator Pitch Summary

- minAvailable: 2 — at least 2 pods must remain.
- maxUnavailable: 1 — at most 1 pod can be down at a time.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-152-kubernetes-q46-what-happens-to-pods-when-you-run-kubectl-drain-on-a-node-l2"></a>
### 152. Kubernetes Q46: What happens to pods when you run kubectl drain on a node [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What happens to pods when you run `kubectl drain` on a node?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

`kubectl drain` does two things:

- **Cordons the node** — marks it unschedulable so no new pods land on it.
- **Evicts all pods** — sends eviction requests (not delete) for every pod. Eviction respects PodDisruptionBudgets.
- DaemonSet pods (need `--ignore-daemonsets` flag to proceed).

##### 2️⃣ Remediation & Permanent Safeguards

Exceptions — these pods are NOT evicted by default: After drain: the node is empty and safe to maintain/terminate. ---

- Pods with local storage (need `--delete-emptydir-data` flag).
- Pods not managed by a controller (standalone pods) — drain will fail unless you force it.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Cordons the node — marks it unschedulable so no new pods land on it..

#### ⏱️ 60-Second Elevator Pitch Summary

- Cordons the node — marks it unschedulable so no new pods land on it.
- Evicts all pods — sends eviction requests (not delete) for every pod. Eviction respects PodDisrup...
- DaemonSet pods (need --ignore-daemonsets flag to proceed).

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-153-kubernetes-q47-explain-how-the-kubernetes-scheduler-makes-a-placement-decision-for-a-new-pod-l3"></a>
### 153. Kubernetes Q47: Explain how the Kubernetes scheduler makes a placement decision for a new pod [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Explain how the Kubernetes scheduler makes a placement decision for a new pod."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

The scheduler goes through two phases:

- Does the node have enough CPU and memory?
- Does the node match the pod's `nodeSelector`?
- Does the pod tolerate the node's taints?
- Are the required volumes available in that zone?
- Does the pod's affinity/anti-affinity rule allow this node?

##### 2️⃣ Remediation & Permanent Safeguards

**Phase 1: Filtering (Predicates)** Eliminate nodes that can't run the pod: **Phase 2: Scoring (Priorities)** Rank the remaining nodes: The highest-scoring node wins. If tied, a random one is picked. The scheduler then writes the chosen node name into the pod's spec (`nodeName` field), and the kubelet on that node picks it up and starts the pod. ---

- Least requested resources (prefer emptier nodes for better bin-packing).
- Affinity preference scores.
- Topology spread.
- Image locality (prefer nodes that already have the image pulled).

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Does the node have enough CPU and memory?.

#### ⏱️ 60-Second Elevator Pitch Summary

- Does the node have enough CPU and memory?
- Does the node match the pod's nodeSelector?
- Does the pod tolerate the node's taints?

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-154-kubernetes-q48-what-is-a-limitrange-and-why-would-you-use-it-l2"></a>
### 154. Kubernetes Q48: What is a LimitRange and why would you use it [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is a LimitRange and why would you use it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

A LimitRange sets default and maximum resource requests/limits for pods in a namespace. If a pod doesn't specify resources, LimitRange fills in defaults.

- **Prevent runaway pods** — without limits, one pod can consume all node CPU/memory.
- **Ensure HPA works** — HPA needs resource requests set. LimitRange auto-sets them.
- **Fair resource sharing** — prevent a single team's namespace from monopolizing the cluster.

##### 2️⃣ Remediation & Permanent Safeguards

Why use it: Example: ---

```bash
limits:
- default:
    cpu: 500m
    memory: 256Mi
  defaultRequest:
    cpu: 100m
    memory: 128Mi
  type: Container
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Prevent runaway pods — without limits, one pod can consume all node CPU/memory..

#### ⏱️ 60-Second Elevator Pitch Summary

- Prevent runaway pods — without limits, one pod can consume all node CPU/memory.
- Ensure HPA works — HPA needs resource requests set. LimitRange auto-sets them.
- Fair resource sharing — prevent a single team's namespace from monopolizing the cluster.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-155-kubernetes-q49-you-have-a-multi-tenant-cluster-where-different-teams-share-the-cluster-how-do-you-isolate-them-l3"></a>
### 155. Kubernetes Q49: You have a multi-tenant cluster where different teams share the cluster How do you isolate them [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"You have a multi-tenant cluster where different teams share the cluster. How do you isolate them?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Soft multi-tenancy in Kubernetes (hard isolation requires separate clusters):

- **Namespaces** — one namespace per team.
- **RBAC** — teams can only access their own namespace.
- **ResourceQuotas** — limit total CPU/memory/pods per namespace.
- **LimitRanges** — default limits per pod/container.

##### 2️⃣ Remediation & Permanent Safeguards

True hard isolation (different teams can't see each other's API resources at all) requires separate clusters or a multi-tenant solution like vCluster. ---

- **NetworkPolicies** — namespace-to-namespace traffic blocked by default.
- **Pod Security Admission** — enforce security baselines (no privileged pods, no hostPath, etc.).
- **OPA/Gatekeeper or Kyverno** — custom policy enforcement (e.g., all images must come from internal registry).

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Namespaces — one namespace per team..

#### ⏱️ 60-Second Elevator Pitch Summary

- Namespaces — one namespace per team.
- RBAC — teams can only access their own namespace.
- ResourceQuotas — limit total CPU/memory/pods per namespace.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-156-kubernetes-q50-explain-the-difference-between-kubectl-apply-and-kubectl-create-when-would-you-use-each-l3"></a>
### 156. Kubernetes Q50: Explain the difference between kubectl apply and kubectl create When would you use each [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Explain the difference between `kubectl apply` and `kubectl create`. When would you use each?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

In CI/CD pipelines, always use `kubectl apply` — it's idempotent. Running the pipeline twice won't fail.

- **`kubectl create`** — imperative. Creates the resource. Fails if it already exists. Good for one-time resource creation.
- **`kubectl apply`** — declarative. Creates if not exists, updates if it does. Tracks changes using the `kubectl.kubernetes.io/last-applied-configuration` annotation. Good for GitOps and automation.

##### 2️⃣ Remediation & Permanent Safeguards

Use `kubectl create` when you specifically want the command to fail if the resource exists (e.g., to prevent accidental overwrites in a script). `kubectl apply` with `--server-side` (SSA) is the modern approach — the server handles merge strategy instead of the client annotation. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: kubectl create — imperative. Creates the resource. Fails if it already exists. Good for one-time resource creation..

#### ⏱️ 60-Second Elevator Pitch Summary

- kubectl create — imperative. Creates the resource. Fails if it already exists. Good for one-time ...
- kubectl apply — declarative. Creates if not exists, updates if it does. Tracks changes using the ...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-157-kubernetes-q51-your-readiness-probe-keeps-failing-even-though-the-app-is-working-fine-what-could-be-wrong-l2"></a>
### 157. Kubernetes Q51: Your readiness probe keeps failing even though the app is working fine What could be wrong [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Your readiness probe keeps failing even though the app is working fine. What could be wrong?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Debug: `kubectl describe pod` shows probe failure reason. Also exec into the pod and manually curl the readiness endpoint to see what it returns.

- **Wrong port or path** — probe is checking a different port/endpoint than the app actually serves.
- **Probe timeout too short** — if the app takes 2 seconds to respond and `timeoutSeconds: 1`, it always times out.
- **App returns non-200 for the health path under load** — the readiness endpoint has a bug.

##### 2️⃣ Remediation & Permanent Safeguards

---

- **initialDelaySeconds too short** — app needs more time to start before readiness checks begin.
- **Checking the wrong container port name** — if using `port: http` and the port isn't named, it fails.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Wrong port or path — probe is checking a different port/endpoint than the app actually serves..

#### ⏱️ 60-Second Elevator Pitch Summary

- Wrong port or path — probe is checking a different port/endpoint than the app actually serves.
- Probe timeout too short — if the app takes 2 seconds to respond and timeoutSeconds: 1, it always ...
- App returns non-200 for the health path under load — the readiness endpoint has a bug.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-158-kubernetes-q52-what-is-the-difference-between-liveness-and-readiness-probes-give-a-scenario-where-each-is-important-l2"></a>
### 158. Kubernetes Q52: What is the difference between liveness and readiness probes Give a scenario where each is important [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is the difference between liveness and readiness probes? Give a scenario where each is important."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Key: failed liveness = restart. Failed readiness = remove from load balancer rotation, but don't restart.

- **Liveness probe** — "is this container still alive?" If it fails, Kubernetes restarts the container. Use for detecting deadlocks or infinite loops where the process is running but not making progress.
- Scenario: A Java app has a thread deadlock. The JVM is running but requests hang forever. Liveness probe detects no HTTP response → restarts container.
- **Readiness probe** — "is this container ready to serve traffic?" If it fails, the pod is removed from Service endpoints. Use for apps that need warmup time or temporarily can't serve (e.g., during a DB connection retry).

##### 2️⃣ Remediation & Permanent Safeguards

---

- Scenario: App just started and is loading a 5GB ML model. Readiness fails until load completes. No traffic is sent yet. App is not restarted (liveness probe is fine).

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Liveness probe — "is this container still alive?" If it fails, Kubernetes restarts the container. Use for detecting deadlocks or i.

#### ⏱️ 60-Second Elevator Pitch Summary

- Liveness probe — "is this container still alive?" If it fails, Kubernetes restarts the container....
- Scenario: A Java app has a thread deadlock. The JVM is running but requests hang forever. Livenes...
- Readiness probe — "is this container ready to serve traffic?" If it fails, the pod is removed fro...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-159-kubernetes-q53-describe-the-pod-lifecycle-from-kubectl-apply-to-the-app-serving-traffic-l3"></a>
### 159. Kubernetes Q53: Describe the pod lifecycle from kubectl apply to the app serving traffic [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Describe the pod lifecycle from `kubectl apply` to the app serving traffic."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

---

- **API server** receives the pod spec, validates it, stores it in etcd. Pod status: `Pending`.
- **kube-scheduler** notices the unscheduled pod, runs filtering + scoring, writes the `nodeName` to the pod spec.
- **kubelet on the chosen node** watches for pods assigned to it. Sees the new pod.
- **kubelet calls the CRI** (Container Runtime Interface — containerd/CRI-O) to pull the image.
- **Init containers run** sequentially to completion.

##### 2️⃣ Remediation & Permanent Safeguards

Execute the resolution runbook and verify workload health:

- **Main containers start**. `postStart` lifecycle hook runs if defined.
- **Liveness and readiness probes start** (after `initialDelaySeconds`).
- Once **readiness probe passes**, kube-proxy adds the pod IP to the Service endpoints.
- **Traffic flows** to the pod.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: API server receives the pod spec, validates it, stores it in etcd. Pod status: Pending..

#### ⏱️ 60-Second Elevator Pitch Summary

- API server receives the pod spec, validates it, stores it in etcd. Pod status: Pending.
- kube-scheduler notices the unscheduled pod, runs filtering + scoring, writes the nodeName to the ...
- kubelet on the chosen node watches for pods assigned to it. Sees the new pod.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-160-kubernetes-q54-someone-applied-a-bad-networkpolicy-thats-blocking-all-traffic-in-the-cluster-how-do-you-recover-l2"></a>
### 160. Kubernetes Q54: Someone applied a bad NetworkPolicy thats blocking all traffic in the cluster How do you recover [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Someone applied a bad NetworkPolicy that's blocking all traffic in the cluster. How do you recover?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Prevention:

- **Identify the policy**: `kubectl get networkpolicy -A` — list all NetworkPolicies across namespaces.
- **Delete the bad one**: `kubectl delete networkpolicy  -n `.
- Traffic should restore immediately after deletion (NetworkPolicy is applied in near-real-time by the CNI plugin).
- Always test NetworkPolicy changes in a staging namespace first.

##### 2️⃣ Remediation & Permanent Safeguards

---

- Use `kubectl apply --dry-run=server` to validate.
- For complex policies, use tools like Cilium's policy editor to visualize impact before applying.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Identify the policy: kubectl get networkpolicy -A — list all NetworkPolicies across namespaces..

#### ⏱️ 60-Second Elevator Pitch Summary

- Identify the policy: kubectl get networkpolicy -A — list all NetworkPolicies across namespaces.
- Delete the bad one: kubectl delete networkpolicy  -n .
- Traffic should restore immediately after deletion (NetworkPolicy is applied in near-real-time by ...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-161-kubernetes-q55-what-is-the-role-of-etcd-in-kubernetes-and-what-happens-if-etcd-goes-down-l3"></a>
### 161. Kubernetes Q55: What is the role of etcd in Kubernetes and what happens if etcd goes down [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is the role of etcd in Kubernetes and what happens if etcd goes down?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

etcd is the key-value store that is Kubernetes' "brain." Every cluster state (pod specs, node info, secrets, configmaps, events) is stored in etcd.

- **Existing pods keep running** — kubelet runs pods independently of the API server.
- **No new pods can be created** — API server can't write new state.
- **No changes work** — no scaling, no new deployments, no config changes.

##### 2️⃣ Remediation & Permanent Safeguards

If etcd goes down: Recovery: restore etcd from a snapshot backup. This is why etcd backups are critical (using `etcdctl snapshot save`). Production setup: etcd should have an **odd number of nodes (3, 5)** for quorum. With 3 nodes, cluster can tolerate 1 failure. With 5 nodes, 2 failures. ---

- **The cluster is effectively read-only and frozen**.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Existing pods keep running — kubelet runs pods independently of the API server..

#### ⏱️ 60-Second Elevator Pitch Summary

- Existing pods keep running — kubelet runs pods independently of the API server.
- No new pods can be created — API server can't write new state.
- No changes work — no scaling, no new deployments, no config changes.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-162-kubernetes-q56-how-do-you-pass-sensitive-configuration-like-db-passwords-to-a-pod-without-hardcoding-them-l2"></a>
### 162. Kubernetes Q56: How do you pass sensitive configuration (like DB passwords) to a pod without hardcoding them [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you pass sensitive configuration (like DB passwords) to a pod without hardcoding them?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Use **Kubernetes Secrets**:

- Create a secret: `kubectl create secret generic db-creds --from-literal=password=mypassword`
- Reference in pod as env var:

##### 2️⃣ Remediation & Permanent Safeguards

Or mount as a file: File mounting is more secure — env vars can leak in logs and process listings. Also avoid printing env vars in app error messages. ---

```bash
env:
- name: DB_PASSWORD
  valueFrom:
    secretKeyRef:
      name: db-creds
      key: password
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Create a secret: kubectl create secret generic db-creds --from-literal=password=mypassword.

#### ⏱️ 60-Second Elevator Pitch Summary

- Create a secret: kubectl create secret generic db-creds --from-literal=password=mypassword
- Reference in pod as env var:

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-163-kubernetes-q57-you-need-to-run-a-pod-that-requires-access-to-the-host-network-like-a-network-monitoring-tool-how-do-you-configure-this-l3"></a>
### 163. Kubernetes Q57: You need to run a pod that requires access to the host network (like a network monitoring tool) How do you configure this [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"You need to run a pod that requires access to the host network (like a network monitoring tool). How do you configure this?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

`hostNetwork: true` makes the pod share the node's network namespace. It can bind to host ports and see all host network interfaces.

- The pod can sniff all traffic on the node.
- Port conflicts — if the pod binds port 80, it conflicts with anything else on port 80 on the host.
- Should only be used for legitimate infrastructure tools (network debuggers, CNI components).

##### 2️⃣ Remediation & Permanent Safeguards

Security implications: ---

- Block with PSA policy in production namespaces.

```bash
spec:
  hostNetwork: true
  hostPID: true  # if also needs host PID namespace
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: The pod can sniff all traffic on the node..

#### ⏱️ 60-Second Elevator Pitch Summary

- The pod can sniff all traffic on the node.
- Port conflicts — if the pod binds port 80, it conflicts with anything else on port 80 on the host.
- Should only be used for legitimate infrastructure tools (network debuggers, CNI components).

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-164-kubernetes-q58-explain-the-concept-of-resource-requests-vs-limits-what-happens-if-you-only-set-limits-and-not-requests-l2"></a>
### 164. Kubernetes Q58: Explain the concept of resource requests vs limits What happens if you only set limits and not requests [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Explain the concept of resource requests vs limits. What happens if you only set limits and not requests?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

If you only set limits and not requests: Kubernetes sets requests equal to limits. This can make scheduling harder because the scheduler thinks each pod needs the full limit amount even if actual usage is much less.

- **Request** — the guaranteed amount. Scheduler uses this to decide which node has enough room.
- **Limit** — the maximum. Container is throttled (CPU) or killed (memory) if it exceeds this.
- Set requests accurately based on average usage.

##### 2️⃣ Remediation & Permanent Safeguards

If you set neither: pod gets `BestEffort` QoS class — it's the first to be evicted under node memory pressure. Recommended practice: ---

- Set limits higher to allow burst.
- For CPU: it's okay to have a 5x ratio. For memory: be careful — exceeding limit = OOM kill.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Request — the guaranteed amount. Scheduler uses this to decide which node has enough room..

#### ⏱️ 60-Second Elevator Pitch Summary

- Request — the guaranteed amount. Scheduler uses this to decide which node has enough room.
- Limit — the maximum. Container is throttled (CPU) or killed (memory) if it exceeds this.
- Set requests accurately based on average usage.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-165-kubernetes-q59-what-are-the-three-qos-classes-in-kubernetes-and-how-does-each-affect-eviction-l3"></a>
### 165. Kubernetes Q59: What are the three QoS classes in Kubernetes and how does each affect eviction [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What are the three QoS classes in Kubernetes and how does each affect eviction?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

When a node runs out of memory, kubelet evicts pods in this order: BestEffort → Burstable (lowest priority score first) → Guaranteed.

- **Guaranteed** — `requests == limits` for all containers. Both CPU and memory. Highest priority. Evicted last.
- **Burstable** — at least one container has requests < limits, or not all containers have both set. Medium priority.
- **BestEffort** — no requests or limits set at all. Lowest priority. Evicted first when node is under memory pressure.

##### 2️⃣ Remediation & Permanent Safeguards

For critical production workloads: use **Guaranteed** QoS (set requests = limits for memory at minimum) to protect them from eviction. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Guaranteed — requests == limits for all containers. Both CPU and memory. Highest priority. Evicted last..

#### ⏱️ 60-Second Elevator Pitch Summary

- Guaranteed — requests == limits for all containers. Both CPU and memory. Highest priority. Evicte...
- Burstable — at least one container has requests < limits, or not all containers have both set. Me...
- BestEffort — no requests or limits set at all. Lowest priority. Evicted first when node is under ...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-166-kubernetes-q60-you-have-a-multi-container-pod-sidecar-pattern-how-do-the-containers-share-data-with-each-other-l2"></a>
### 166. Kubernetes Q60: You have a multi-container pod (sidecar pattern) How do the containers share data with each other [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"You have a multi-container pod (sidecar pattern). How do the containers share data with each other?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Containers in the same pod share:

- **Network namespace** — they can communicate via `localhost`. If container A serves on port 8080, container B can reach it at `localhost:8080`.
- **Volumes** — mount a shared `emptyDir` volume. Both containers read/write to the same directory.

##### 2️⃣ Remediation & Permanent Safeguards

Example use case — log shipping sidecar: main app writes logs to `/var/log/app` (emptyDir volume), Fluentd sidecar reads from the same path and ships to Elasticsearch. They do NOT share the filesystem by default — only through shared volumes. --- **Q61-Q100 — Additional Kubernetes Scenarios** ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Network namespace — they can communicate via localhost. If container A serves on port 8080, container B can reach it at localhost:.

#### ⏱️ 60-Second Elevator Pitch Summary

- Network namespace — they can communicate via localhost. If container A serves on port 8080, conta...
- Volumes — mount a shared emptyDir volume. Both containers read/write to the same directory.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-167-kubernetes-q61-what-is-the-difference-between-emptydir-and-hostpath-volumes-l2"></a>
### 167. Kubernetes Q61: What is the difference between emptyDir and hostPath volumes [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is the difference between `emptyDir` and `hostPath` volumes?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Use `emptyDir` for temporary shared data. Avoid `hostPath` in production unless absolutely necessary (e.g., running Docker-in-Docker or accessing host logs).

- `emptyDir` — temporary directory created when pod starts, deleted when pod is removed. Shared between containers in the pod. Good for scratch space or sidecar data sharing.
- `hostPath` — mounts a path from the host node's filesystem. Survives pod restarts as long as the pod stays on the same node. Risky in production — pod is now tied to a specific node and can access host files.

##### 2️⃣ Remediation & Permanent Safeguards

---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: emptyDir — temporary directory created when pod starts, deleted when pod is removed. Shared between containers in the pod. Good fo.

#### ⏱️ 60-Second Elevator Pitch Summary

- emptyDir — temporary directory created when pod starts, deleted when pod is removed. Shared betwe...
- hostPath — mounts a path from the host node's filesystem. Survives pod restarts as long as the po...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-168-kubernetes-q62-a-cluster-autoscaler-is-not-scaling-up-even-though-pods-are-pending-what-could-be-wrong-l3"></a>
### 168. Kubernetes Q62: A cluster-autoscaler is not scaling up even though pods are Pending What could be wrong [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"A cluster-autoscaler is not scaling up even though pods are Pending. What could be wrong?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Check: CA logs — `kubectl logs -n kube-system ` — it logs exactly why it's not scaling.

- **Pod is unschedulable for a reason other than resources** — e.g., node affinity requires a specific label that no node type has. CA won't add nodes it can't schedule the pod on.
- **Max node count reached** — CA has a configured max. `--max-nodes-total` or per-node-group limit.
- **Pod has `cluster-autoscaler.kubernetes.io/safe-to-evict: false`** — CA may refuse to scale if eviction of existing pods is blocked.
- **Cooldown period** — CA has a scale-up cooldown (default 10 min). May be waiting.

##### 2️⃣ Remediation & Permanent Safeguards

---

- **Budget exhausted** — cloud account has hit EC2/VM quota.
- **CA can't provision the requested instance type** — spot capacity unavailable.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Pod is unschedulable for a reason other than resources — e.g., node affinity requires a specific label that no node type has. CA w.

#### ⏱️ 60-Second Elevator Pitch Summary

- Pod is unschedulable for a reason other than resources — e.g., node affinity requires a specific ...
- Max node count reached — CA has a configured max. --max-nodes-total or per-node-group limit.
- Pod has cluster-autoscaler.kubernetes.io/safe-to-evict: false — CA may refuse to scale if evictio...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-169-kubernetes-q63-how-do-you-roll-back-a-helm-release-l2"></a>
### 169. Kubernetes Q63: How do you roll back a Helm release [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you roll back a Helm release?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Helm keeps a history of all deployed revisions (stored as Secrets in the namespace). Each revision has a snapshot of the values and chart used. If `--history-max` is set, older revisions are pruned automatically, limiting how far back you can roll. ---

```bash
helm history <release-name>         # see all revisions
helm rollback <release-name> 2      # roll back to revision 2
helm rollback <release-name>        # roll back to previous revision
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Helm keeps a history of all deployed revisions (stored as Secrets in the namespace). Each revision has a snapshot of the values an.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: bash
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-170-kubernetes-q64-what-is-helm-and-why-is-it-used-instead-of-raw-yaml-l2"></a>
### 170. Kubernetes Q64: What is Helm and why is it used instead of raw YAML [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is Helm and why is it used instead of raw YAML?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Helm is a package manager for Kubernetes. A Helm chart bundles all the Kubernetes YAML for an application (Deployment, Service, ConfigMap, Ingress, etc.) with templating.

- **Reusability** — parameterize with values instead of duplicating YAML per environment.
- **Versioning** — charts have versions. Rollback to a previous chart version.
- **Dependency management** — a chart can depend on other charts (e.g., your app chart depends on a Redis chart).

##### 2️⃣ Remediation & Permanent Safeguards

Why use it: Downside: Helm templates can get complex. For simpler cases, Kustomize is often cleaner. ---

- **Community charts** — Artifact Hub has thousands of pre-built charts for common software.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Reusability — parameterize with values instead of duplicating YAML per environment..

#### ⏱️ 60-Second Elevator Pitch Summary

- Reusability — parameterize with values instead of duplicating YAML per environment.
- Versioning — charts have versions. Rollback to a previous chart version.
- Dependency management — a chart can depend on other charts (e.g., your app chart depends on a Red...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-171-kubernetes-q65-explain-how-kubernetes-handles-pod-eviction-during-node-memory-pressure-l3"></a>
### 171. Kubernetes Q65: Explain how Kubernetes handles pod eviction during node memory pressure [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Explain how Kubernetes handles pod eviction during node memory pressure."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

kubelet monitors node memory usage against eviction thresholds:

- **Soft eviction** — e.g., `memory.available < 500Mi`. kubelet gives pods a grace period (`eviction-soft-grace-period`, default 90s) to shut down before killing.
- **Hard eviction** — e.g., `memory.available < 100Mi`. kubelet immediately kills pods with no grace period.
- BestEffort pods first.

##### 2️⃣ Remediation & Permanent Safeguards

Eviction order: After eviction, the node reports `MemoryPressure` condition and is tainted. New pods won't schedule there until pressure resolves. ---

- Burstable pods that exceed their memory request (most over request first).
- Guaranteed pods (last resort).

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Soft eviction — e.g., memory.available . kubelet gives pods a grace period (eviction-soft-grace-period, default 90s) to shut down .

#### ⏱️ 60-Second Elevator Pitch Summary

- Soft eviction — e.g., memory.available . kubelet gives pods a grace period (eviction-soft-grace-p...
- Hard eviction — e.g., memory.available . kubelet immediately kills pods with no grace period.
- BestEffort pods first.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-172-kubernetes-q66-what-is-the-purpose-of-terminationgraceperiodseconds-l2"></a>
### 172. Kubernetes Q66: What is the purpose of terminationGracePeriodSeconds [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is the purpose of `terminationGracePeriodSeconds`?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

When a pod is deleted, Kubernetes sends `SIGTERM` to the container and waits `terminationGracePeriodSeconds` (default: 30s) for the app to shut down gracefully. After the grace period, `SIGKILL` is sent.

- Your app should handle `SIGTERM` by finishing in-flight requests and closing connections before exiting.
- If your app needs more than 30s to drain (e.g., it's processing long jobs), increase the grace period.
- If `preStop` hook is defined, it runs before SIGTERM and counts against the grace period.

##### 2️⃣ Remediation & Permanent Safeguards

Why it matters: For web servers: graceful shutdown means finishing current HTTP requests. For consumers: finish processing the current message before stopping. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Your app should handle SIGTERM by finishing in-flight requests and closing connections before exiting..

#### ⏱️ 60-Second Elevator Pitch Summary

- Your app should handle SIGTERM by finishing in-flight requests and closing connections before exi...
- If your app needs more than 30s to drain (e.g., it's processing long jobs), increase the grace pe...
- If preStop hook is defined, it runs before SIGTERM and counts against the grace period.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-173-kubernetes-q67-you-need-to-run-a-pod-that-will-only-start-after-a-specific-configmap-exists-in-the-cluster-how-do-you-implement-this-l3"></a>
### 173. Kubernetes Q67: You need to run a pod that will only start after a specific ConfigMap exists in the cluster How do you implement this [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"You need to run a pod that will only start after a specific ConfigMap exists in the cluster. How do you implement this?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use an **init container** that polls for the ConfigMap: The init container keeps checking every 5 seconds until the ConfigMap exists, then exits (allowing the main container to start). This pattern is common for sequencing: wait for a database to be ready, wait for a service to exist, wait for a secret to be populated. ---

```bash
initContainers:
- name: wait-for-config
  image: bitnami/kubectl
  command: ['sh', '-c', 'until kubectl get configmap my-config; do echo waiting; sleep 5; done']
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use an init container that polls for the ConfigMap:.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use an init container that polls for the ConfigMap:
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-174-kubernetes-q68-what-is-the-purpose-of-podantiaffinity-with-topologykey-topologykubernetesio-zone-l2"></a>
### 174. Kubernetes Q68: What is the purpose of podAntiAffinity with topologyKey topologykubernetesio/zone [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is the purpose of `podAntiAffinity` with `topologyKey: topology.kubernetes.io/zone`?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

This spreads pods across availability zones rather than just across nodes. If your cluster spans 3 AZs (us-east-1a, 1b, 1c), this anti-affinity ensures no two pods of the same app land in the same AZ. Why: Even with node anti-affinity, all your "different nodes" could be in the same AZ. If that AZ goes down, you lose everything. Zone-spread anti-affinity ensures true high availability across data center failures. Combine with `topologySpreadConstraints` for finer control over pod distribution across zones and nodes. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: This spreads pods across availability zones rather than just across nodes. If your cluster spans 3 AZs (us-east-1a, 1b, 1c), this .

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: This spreads pods across availability zones rather than just across nodes. If your cluster span
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-175-kubernetes-q69-describe-the-container-storage-interface-csi-and-why-it-replaced-in-tree-volume-plugins-l3"></a>
### 175. Kubernetes Q69: Describe the Container Storage Interface (CSI) and why it replaced in-tree volume plugins [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Describe the Container Storage Interface (CSI) and why it replaced in-tree volume plugins."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

In-tree volume plugins (like the old AWS EBS plugin built into kubelet) had problems:

- They had to be updated with Kubernetes releases.
- Bugs in storage plugins could crash kubelet.
- Storage vendors couldn't release independently of Kubernetes.
- PVC created → external-provisioner (CSI sidecar) calls the CSI driver to provision a volume.

##### 2️⃣ Remediation & Permanent Safeguards

**CSI (Container Storage Interface)** is a standard API that lets storage vendors write drivers that run as pods in the cluster, independent of Kubernetes core. Flow: Vendors like AWS (EBS CSI), Azure Disk, GCP PD, and Portworx all now have CSI drivers. In-tree plugins are deprecated and being removed. ---

- Pod scheduled → node-driver-registrar mounts the volume on the node.
- Container starts with the volume attached.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: They had to be updated with Kubernetes releases..

#### ⏱️ 60-Second Elevator Pitch Summary

- They had to be updated with Kubernetes releases.
- Bugs in storage plugins could crash kubelet.
- Storage vendors couldn't release independently of Kubernetes.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-176-kubernetes-q70-what-is-a-mutating-admission-webhook-and-give-a-practical-use-case-l3"></a>
### 176. Kubernetes Q70: What is a mutating admission webhook and give a practical use case [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is a mutating admission webhook and give a practical use case?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Admission webhooks intercept API requests before they're stored in etcd. **Mutating** webhooks can modify the request (add/change fields). **Validating** webhooks can accept or reject it.

- **Istio/Linkerd sidecar injection** — automatically inject the sidecar proxy container into every pod in labeled namespaces.
- **Default resource limits** — if a pod has no resource limits, auto-add safe defaults.
- **Label injection** — add team/cost-center labels to all pods.

##### 2️⃣ Remediation & Permanent Safeguards

Practical use cases for mutating webhooks: The webhook is an HTTPS server (usually running as a pod). Kubernetes sends the resource spec to it, the server returns a JSON Patch with modifications. --- **Q71-Q100. Rapid-fire Kubernetes Scenarios**

- **Image tag enforcement** — replace `latest` tag with the actual SHA digest.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Istio/Linkerd sidecar injection — automatically inject the sidecar proxy container into every pod in labeled namespaces..

#### ⏱️ 60-Second Elevator Pitch Summary

- Istio/Linkerd sidecar injection — automatically inject the sidecar proxy container into every pod...
- Default resource limits — if a pod has no resource limits, auto-add safe defaults.
- Label injection — add team/cost-center labels to all pods.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-177-kubernetes-q71-pod-shows-errimagepull-l1"></a>
### 177. Kubernetes Q71: Pod shows ErrImagePull [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L1` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Pod shows `ErrImagePull`."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Image not found or wrong tag. Check image name/tag. For private registry, ensure imagePullSecret is configured.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Image not found or wrong tag. Check image name/tag. For private registry, ensure imagePullSecret is configured..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Image not found or wrong tag. Check image name/tag. For private registry, ensure imagePullSecre
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-178-kubernetes-q72-deployment-has-0-ready-pods-but-desired-is-3-l2"></a>
### 178. Kubernetes Q72: Deployment has 0 ready pods but desired is 3 [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Deployment has 0 ready pods but desired is 3."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

All pods failing readiness. Check probe config and app logs.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: All pods failing readiness. Check probe config and app logs..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: All pods failing readiness. Check probe config and app logs.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-179-kubernetes-q73-how-do-you-scale-a-deployment-to-5-replicas-l1"></a>
### 179. Kubernetes Q73: How do you scale a deployment to 5 replicas [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L1` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you scale a deployment to 5 replicas?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`kubectl scale deployment  --replicas=5` or update spec.replicas.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: kubectl scale deployment  --replicas=5 or update spec.replicas..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: kubectl scale deployment  --replicas=5 or update spec.replicas.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-180-kubernetes-q74-nodeport-service-not-reachable-from-outside-l2"></a>
### 180. Kubernetes Q74: NodePort service not reachable from outside [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"NodePort service not reachable from outside."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Check firewall/security group rules allow the NodePort (30000-32767) range.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Check firewall/security group rules allow the NodePort (30000-32767) range..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Check firewall/security group rules allow the NodePort (30000-32767) range.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-181-kubernetes-q75-two-pods-cant-communicate-even-though-networkpolicy-allows-it-l2"></a>
### 181. Kubernetes Q75: Two pods cant communicate even though NetworkPolicy allows it [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Two pods can't communicate even though NetworkPolicy allows it."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

CNI plugin may not support NetworkPolicy. Check CNI (Flannel doesn't, Calico does).

#### 🎯 Key Architectural Takeaway
> Pro-Tip: CNI plugin may not support NetworkPolicy. Check CNI (Flannel doesn't, Calico does)..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: CNI plugin may not support NetworkPolicy. Check CNI (Flannel doesn't, Calico does).
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-182-kubernetes-q76-how-do-you-upgrade-kubernetes-version-with-zero-downtime-l3"></a>
### 182. Kubernetes Q76: How do you upgrade Kubernetes version with zero downtime [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you upgrade Kubernetes version with zero downtime?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Upgrade control plane first (API server, etcd, scheduler). Then drain, upgrade, uncordon worker nodes one by one.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Upgrade control plane first (API server, etcd, scheduler). Then drain, upgrade, uncordon worker nodes one by one..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Upgrade control plane first (API server, etcd, scheduler). Then drain, upgrade, uncordon worker
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-183-kubernetes-q77-ingress-shows-address-pending-l2"></a>
### 183. Kubernetes Q77: Ingress shows Address <pending> [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Ingress shows `Address: `."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

No LoadBalancer IP assigned yet. On bare-metal, need MetalLB. On cloud, wait 1-2 min for cloud LB provisioning.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: No LoadBalancer IP assigned yet. On bare-metal, need MetalLB. On cloud, wait 1-2 min for cloud LB provisioning..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: No LoadBalancer IP assigned yet. On bare-metal, need MetalLB. On cloud, wait 1-2 min for cloud
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-184-kubernetes-q78-how-do-you-get-logs-from-all-pods-of-a-deployment-l1"></a>
### 184. Kubernetes Q78: How do you get logs from all pods of a deployment [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L1` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you get logs from all pods of a deployment?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`kubectl logs -l app=` or use label selector.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: kubectl logs -l app= or use label selector..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: kubectl logs -l app= or use label selector.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-185-kubernetes-q79-horizontal-pod-autoscaler-shows-unknown-50-for-current-metric-l2"></a>
### 185. Kubernetes Q79: Horizontal Pod Autoscaler shows unknown/50% for current metric [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Horizontal Pod Autoscaler shows `unknown/50%` for current metric."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

metrics-server not installed or pods have no resource requests set.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: metrics-server not installed or pods have no resource requests set..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: metrics-server not installed or pods have no resource requests set.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-186-kubernetes-q80-etcd-backup-failed-recovery-steps-l3"></a>
### 186. Kubernetes Q80: etcd backup failed Recovery steps [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"etcd backup failed. Recovery steps?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`etcdctl snapshot save backup.db`. Restore: stop API server, restore snapshot, restart.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: etcdctl snapshot save backup.db. Restore: stop API server, restore snapshot, restart..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: etcdctl snapshot save backup.db. Restore: stop API server, restore snapshot, restart.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-187-kubernetes-q81-a-developer-accidentally-deleted-a-namespace-how-do-you-recover-l2"></a>
### 187. Kubernetes Q81: A developer accidentally deleted a namespace How do you recover [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"A developer accidentally deleted a namespace. How do you recover?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

From backup/GitOps. There's no undo in kubectl. This is why GitOps (ArgoCD/Flux) matters — re-apply the Git state.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: From backup/GitOps. There's no undo in kubectl. This is why GitOps (ArgoCD/Flux) matters — re-apply the Git state..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: From backup/GitOps. There's no undo in kubectl. This is why GitOps (ArgoCD/Flux) matters — re-a
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-188-kubernetes-q82-pod-shows-terminating-for-hours-and-wont-delete-l2"></a>
### 188. Kubernetes Q82: Pod shows Terminating for hours and wont delete [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Pod shows `Terminating` for hours and won't delete."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Force delete: `kubectl delete pod  --grace-period=0 --force`. Usually caused by finalizers or stuck volumes.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Force delete: kubectl delete pod  --grace-period=0 --force. Usually caused by finalizers or stuck volumes..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Force delete: kubectl delete pod  --grace-period=0 --force. Usually caused by finalizers or stu
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-189-kubernetes-q83-service-mesh-vs-networkpolicy-when-do-you-use-each-l3"></a>
### 189. Kubernetes Q83: Service mesh vs NetworkPolicy — when do you use each [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Service mesh vs NetworkPolicy — when do you use each?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

NetworkPolicy = L3/L4 (IP/port). Service mesh (Istio/Linkerd) = L7 (HTTP routing, mTLS, retries, circuit breaking). Use both for layered security.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: NetworkPolicy = L3/L4 (IP/port). Service mesh (Istio/Linkerd) = L7 (HTTP routing, mTLS, retries, circuit breaking). Use both for l.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: NetworkPolicy = L3/L4 (IP/port). Service mesh (Istio/Linkerd) = L7 (HTTP routing, mTLS, retries
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-190-kubernetes-q84-how-do-you-make-a-pod-restart-on-config-change-without-a-code-change-l2"></a>
### 190. Kubernetes Q84: How do you make a pod restart on config change without a code change [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you make a pod restart on config change without a code change?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Add annotation with configmap hash: `checksum/config: {{ include (print .Template.BasePath "/configmap.yaml") . | sha256sum }}` in Helm. Or use Reloader operator.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Add annotation with configmap hash: checksum/config: {{ include (print .Template.BasePath "/configmap.yaml") . | sha256sum }} in H.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Add annotation with configmap hash: checksum/config: {{ include (print .Template.BasePath "/con
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-191-kubernetes-q85-a-cronjob-job-ran-but-the-pod-isnt-showing-in-kubectl-get-jobs-l2"></a>
### 191. Kubernetes Q85: A CronJob job ran but the pod isnt showing in kubectl get jobs [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"A CronJob job ran but the pod isn't showing in `kubectl get jobs`."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`successfulJobsHistoryLimit` may be 0 or 1 and old jobs were cleaned. Adjust to keep history.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: successfulJobsHistoryLimit may be 0 or 1 and old jobs were cleaned. Adjust to keep history..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: successfulJobsHistoryLimit may be 0 or 1 and old jobs were cleaned. Adjust to keep history.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-192-kubernetes-q86-your-admission-webhook-is-blocking-all-pod-creation-cluster-wide-how-do-you-recover-l3"></a>
### 192. Kubernetes Q86: Your admission webhook is blocking all pod creation cluster-wide How do you recover [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Your admission webhook is blocking all pod creation cluster-wide. How do you recover?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

If webhook server is down, set `failurePolicy: Ignore` on the webhook or delete the `MutatingWebhookConfiguration` object.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: If webhook server is down, set failurePolicy: Ignore on the webhook or delete the MutatingWebhookConfiguration object..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: If webhook server is down, set failurePolicy: Ignore on the webhook or delete the MutatingWebho
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-193-kubernetes-q87-how-do-you-check-if-a-service-account-has-permission-to-create-pods-l2"></a>
### 193. Kubernetes Q87: How do you check if a service account has permission to create pods [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you check if a service account has permission to create pods?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`kubectl auth can-i create pods --as=system:serviceaccount::`

#### 🎯 Key Architectural Takeaway
> Pro-Tip: kubectl auth can-i create pods --as=system:serviceaccount::.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: kubectl auth can-i create pods --as=system:serviceaccount::
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-194-kubernetes-q88-what-is-the-difference-between-kubectl-get-and-kubectl-describe-l1"></a>
### 194. Kubernetes Q88: What is the difference between kubectl get and kubectl describe [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L1` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is the difference between `kubectl get` and `kubectl describe`?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`get` = brief summary table. `describe` = full detail including events. Use describe for debugging.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: get = brief summary table. describe = full detail including events. Use describe for debugging..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: get = brief summary table. describe = full detail including events. Use describe for debugging.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-195-kubernetes-q89-you-want-to-run-a-one-off-debug-pod-on-a-specific-node-how-l2"></a>
### 195. Kubernetes Q89: You want to run a one-off debug pod on a specific node How [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"You want to run a one-off debug pod on a specific node. How?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`kubectl debug node/ -it --image=ubuntu` or use `nodeName` field in pod spec.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: kubectl debug node/ -it --image=ubuntu or use nodeName field in pod spec..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: kubectl debug node/ -it --image=ubuntu or use nodeName field in pod spec.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-196-kubernetes-q90-explain-how-kube-proxy-implements-services-using-iptables-l3"></a>
### 196. Kubernetes Q90: Explain how kube-proxy implements Services using iptables [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Explain how kube-proxy implements Services using iptables."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

kube-proxy watches Services/Endpoints. Creates iptables DNAT rules: traffic to ClusterIP is redirected to one of the pod IPs using a round-robin probability chain.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: kube-proxy watches Services/Endpoints. Creates iptables DNAT rules: traffic to ClusterIP is redirected to one of the pod IPs using.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: kube-proxy watches Services/Endpoints. Creates iptables DNAT rules: traffic to ClusterIP is red
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-197-kubernetes-q91-what-is-topology-spread-constraints-and-when-would-you-use-it-over-pod-anti-affinity-l2"></a>
### 197. Kubernetes Q91: What is topology spread constraints and when would you use it over pod anti-affinity [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is topology spread constraints and when would you use it over pod anti-affinity?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

TopologySpreadConstraints gives fine-grained control over pod distribution (e.g., max skew of 1 between zones). Anti-affinity is binary. Use topology spread for better distribution control.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: TopologySpreadConstraints gives fine-grained control over pod distribution (e.g., max skew of 1 between zones). Anti-affinity is b.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: TopologySpreadConstraints gives fine-grained control over pod distribution (e.g., max skew of 1
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-198-kubernetes-q92-a-pod-needs-gpu-resources-how-do-you-configure-it-l2"></a>
### 198. Kubernetes Q92: A pod needs GPU resources How do you configure it [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"A pod needs GPU resources. How do you configure it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Node must have GPU + GPU device plugin installed. Pod requests: `resources.limits: nvidia.com/gpu: 1`. Scheduler finds a node with available GPU.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Node must have GPU + GPU device plugin installed. Pod requests: resources.limits: nvidia.com/gpu: 1. Scheduler finds a node with a.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Node must have GPU + GPU device plugin installed. Pod requests: resources.limits: nvidia.com/gp
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-199-kubernetes-q93-describe-leader-election-in-kubernetes-control-plane-components-l3"></a>
### 199. Kubernetes Q93: Describe leader election in Kubernetes control plane components [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Describe leader election in Kubernetes control plane components."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Scheduler and controller-manager use Lease objects in etcd. Only the leader processes work. Others watch. If leader fails to renew its lease, another takes over. Prevents split-brain in HA setups.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Scheduler and controller-manager use Lease objects in etcd. Only the leader processes work. Others watch. If leader fails to renew.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Scheduler and controller-manager use Lease objects in etcd. Only the leader processes work. Oth
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-200-kubernetes-q94-what-is-a-finalizer-and-when-would-you-use-one-l2"></a>
### 200. Kubernetes Q94: What is a finalizer and when would you use one [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is a finalizer and when would you use one?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Finalizer is a string in `metadata.finalizers`. Prevents object deletion until the finalizer is removed. Use case: ensure external resources (cloud volumes, DNS records) are cleaned up before the Kubernetes object is deleted.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Finalizer is a string in metadata.finalizers. Prevents object deletion until the finalizer is removed. Use case: ensure external r.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Finalizer is a string in metadata.finalizers. Prevents object deletion until the finalizer is r
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-201-kubernetes-q95-how-does-the-kubernetes-garbage-collector-work-l3"></a>
### 201. Kubernetes Q95: How does the Kubernetes garbage collector work [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How does the Kubernetes garbage collector work?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Uses owner references. When a parent object (Deployment) is deleted, GC deletes owned objects (ReplicaSets → Pods) in cascade. `--cascade=orphan` flag leaves children running.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Uses owner references. When a parent object (Deployment) is deleted, GC deletes owned objects (ReplicaSets → Pods) in cascade. --c.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Uses owner references. When a parent object (Deployment) is deleted, GC deletes owned objects (
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-202-kubernetes-q96-how-do-you-run-a-privileged-debug-container-on-a-running-pod-without-modifying-the-pod-spec-l2"></a>
### 202. Kubernetes Q96: How do you run a privileged debug container on a running pod without modifying the pod spec [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you run a privileged debug container on a running pod without modifying the pod spec?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`kubectl debug -it  --image=ubuntu --share-processes --copy-to=debug-pod` — creates a copy of the pod with an extra debug container.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: kubectl debug -it  --image=ubuntu --share-processes --copy-to=debug-pod — creates a copy of the pod with an extra debug container..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: kubectl debug -it  --image=ubuntu --share-processes --copy-to=debug-pod — creates a copy of the
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-203-kubernetes-q97-what-is-the-kubernetes-watch-mechanism-and-how-do-informers-use-it-l3"></a>
### 203. Kubernetes Q97: What is the Kubernetes watch mechanism and how do informers use it [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is the Kubernetes watch mechanism and how do informers use it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

The API server supports a `watch` query param. Client gets a stream of events (ADDED/MODIFIED/DELETED) instead of polling. Informers use this + a local cache to efficiently react to changes without hammering the API server.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: The API server supports a watch query param. Client gets a stream of events (ADDED/MODIFIED/DELETED) instead of polling. Informers.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: The API server supports a watch query param. Client gets a stream of events (ADDED/MODIFIED/DEL
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-204-kubernetes-q98-explain-the-difference-between-kubectl-apply-with-a-file-vs-kubectl-apply-k-kustomize-l2"></a>
### 204. Kubernetes Q98: Explain the difference between kubectl apply with a file vs kubectl apply -k (kustomize) [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Explain the difference between `kubectl apply` with a file vs `kubectl apply -k` (kustomize)."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`-f` applies a single file or directory of raw YAML. `-k` runs Kustomize, applying base + overlays, generating configs, and applying the merged result.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: -f applies a single file or directory of raw YAML. -k runs Kustomize, applying base + overlays, generating configs, and applying t.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: -f applies a single file or directory of raw YAML. -k runs Kustomize, applying base + overlays,
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-205-kubernetes-q99-how-would-you-migrate-a-stateful-workload-from-one-kubernetes-cluster-to-another-with-minimal-downtime-l3"></a>
### 205. Kubernetes Q99: How would you migrate a stateful workload from one Kubernetes cluster to another with minimal downtime [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How would you migrate a stateful workload from one Kubernetes cluster to another with minimal downtime?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

1) Snapshot PVC data (Velero). 2) Deploy workload in new cluster from same Git source. 3) Restore data snapshot to new cluster PVCs. 4) Test new cluster. 5) Switch DNS/load balancer to new cluster. 6) Decommission old cluster.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: 1) Snapshot PVC data (Velero). 2) Deploy workload in new cluster from same Git source. 3) Restore data snapshot to new cluster PVC.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: 1) Snapshot PVC data (Velero). 2) Deploy workload in new cluster from same Git source. 3) Resto
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-206-kubernetes-q100-what-is-keda-and-how-does-it-extend-hpa-l3"></a>
### 206. Kubernetes Q100: What is KEDA and how does it extend HPA [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is KEDA and how does it extend HPA?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

KEDA (Kubernetes Event-Driven Autoscaling) scales pods based on external event sources: Kafka topic lag, RabbitMQ queue depth, HTTP request rate, Azure Service Bus, AWS SQS, cron schedules. Standard HPA only uses CPU/memory. KEDA plugs in as a custom metrics source to HPA, enabling scale-to-zero and event-driven scaling. --- *More Kubernetes scenarios added periodically. PRs welcome.* --- ## 🟤 Additional Kubernetes Scenarios (Q101-Q200) ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: KEDA (Kubernetes Event-Driven Autoscaling) scales pods based on external event sources: Kafka topic lag, RabbitMQ queue depth, HTT.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: KEDA (Kubernetes Event-Driven Autoscaling) scales pods based on external event sources: Kafka t
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-207-kubernetes-q101-how-do-you-expose-a-grpc-service-in-kubernetes-l2"></a>
### 207. Kubernetes Q101: How do you expose a gRPC service in Kubernetes [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you expose a gRPC service in Kubernetes?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use a Service with the correct port and protocol annotation. For Ingress: you need an ingress controller that supports gRPC (nginx-ingress with `nginx.ingress.kubernetes.io/backend-protocol: GRPC` annotation, or Istio). gRPC requires HTTP/2, so TLS is typically required. With Istio: define a VirtualService with gRPC routing rules.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use a Service with the correct port and protocol annotation. For Ingress: you need an ingress controller that supports gRPC (nginx.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use a Service with the correct port and protocol annotation. For Ingress: you need an ingress c
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-208-kubernetes-q102-explain-how-kubernetes-handles-rolling-back-a-daemonset-update-l3"></a>
### 208. Kubernetes Q102: Explain how Kubernetes handles rolling back a DaemonSet update [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Explain how Kubernetes handles rolling back a DaemonSet update."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

DaemonSets support `kubectl rollout undo daemonset/` similar to Deployments. DaemonSet keeps rollout history (configurable via `revisionHistoryLimit`). During rollback, it re-applies the previous pod template spec, updating nodes one by one based on `updateStrategy`. The main difference from Deployments: there's no concept of "unavailable" limit since each node must have exactly one pod.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: DaemonSets support kubectl rollout undo daemonset/ similar to Deployments. DaemonSet keeps rollout history (configurable via revis.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: DaemonSets support kubectl rollout undo daemonset/ similar to Deployments. DaemonSet keeps roll
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-209-kubernetes-q103-a-kubernetes-job-is-stuck-at-0-1-running-and-never-starts-what-do-you-check-l2"></a>
### 209. Kubernetes Q103: A Kubernetes Job is stuck at 0/1 Running and never starts What do you check [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"A Kubernetes Job is stuck at "0/1 Running" and never starts. What do you check?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Same as any pod: `kubectl describe job `, check the created pod's events. Common issues: image pull error, no nodes with enough resources, node selector mismatch, parallelism setting. For Jobs with `completions > 1`, check if `parallelism` is set too low or if previous failed pods are blocking.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Same as any pod: kubectl describe job , check the created pod's events. Common issues: image pull error, no nodes with enough reso.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Same as any pod: kubectl describe job , check the created pod's events. Common issues: image pu
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-210-kubernetes-q104-how-do-you-configure-a-pod-to-get-secrets-from-hashicorp-vault-without-modifying-app-code-l2"></a>
### 210. Kubernetes Q104: How do you configure a pod to get secrets from HashiCorp Vault without modifying app code [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you configure a pod to get secrets from HashiCorp Vault without modifying app code?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use Vault Agent Injector (Vault installed in K8s). Annotate the pod: The Vault Agent sidecar is injected into the pod. It authenticates with Vault using K8s ServiceAccount token, fetches the secrets, and writes them to a shared volume at `/vault/secrets/`. App reads files. No code change needed.

```bash
annotations:
  vault.hashicorp.com/agent-inject: "true"
  vault.hashicorp.com/role: "my-app"
  vault.hashicorp.com/agent-inject-secret-config: "secret/data/myapp"
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use Vault Agent Injector (Vault installed in K8s). Annotate the pod:.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use Vault Agent Injector (Vault installed in K8s). Annotate the pod:
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-211-kubernetes-q105-what-is-the-kubernetes-control-loop-and-how-does-it-apply-to-custom-operators-l3"></a>
### 211. Kubernetes Q105: What is the Kubernetes control loop and how does it apply to custom operators [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is the Kubernetes control loop and how does it apply to custom operators?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

The control loop pattern: watch current state → compare with desired state → take action to reconcile. Controllers (Deployment controller, ReplicaSet controller) do this continuously. Custom operators use the same pattern for custom resources. You define a Custom Resource Definition (CRD) and write a controller that watches those CRs and reconciles. Example: a PostgreSQL operator watches `Postgres` CRs and creates/manages actual Postgres pods, services, and backups. Tools: kubebuilder, Operator SDK.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: The control loop pattern: watch current state → compare with desired state → take action to reconcile. Controllers (Deployment con.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: The control loop pattern: watch current state → compare with desired state → take action to rec
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-212-kubernetes-q106-how-do-you-restrict-a-pod-from-accessing-the-cloud-metadata-endpoint-eg-169254169254-l2"></a>
### 212. Kubernetes Q106: How do you restrict a pod from accessing the cloud metadata endpoint (eg 169254169254) [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you restrict a pod from accessing the cloud metadata endpoint (e.g., 169.254.169.254)?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Without restriction, any pod can query the EC2 metadata endpoint and potentially steal the node's IAM role credentials. Block it with NetworkPolicy: On EKS: use IMDSv2 which requires a hop limit of 1 (pods can't reach it since they're an extra hop). Configure in the launch template.

```bash
spec:
  podSelector: {}  # all pods
  policyTypes: [Egress]
  egress:
  - to:
    - ipBlock:
        cidr: 0.0.0.0/0
        except:
          - 169.254.169.254/32
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Without restriction, any pod can query the EC2 metadata endpoint and potentially steal the node's IAM role credentials. Block it w.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Without restriction, any pod can query the EC2 metadata endpoint and potentially steal the node
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-213-kubernetes-q107-what-is-a-serviceaccount-token-and-when-does-it-expire-l2"></a>
### 213. Kubernetes Q107: What is a ServiceAccount token and when does it expire [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is a ServiceAccount token and when does it expire?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

In K8s 1.21+, ServiceAccount tokens are **bound tokens** — time-limited (default 1 hour), audience-specific, automatically rotated by the kubelet. Older clusters used long-lived JWTs stored as Secrets. Pods access the token at `/var/run/secrets/kubernetes.io/serviceaccount/token`. The kubelet refreshes it before expiry, so the mounted file is always valid.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: In K8s 1.21+, ServiceAccount tokens are bound tokens — time-limited (default 1 hour), audience-specific, automatically rotated by .

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: In K8s 1.21+, ServiceAccount tokens are bound tokens — time-limited (default 1 hour), audience-
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-214-kubernetes-q108-explain-kubernetes-operator-pattern-vs-helm-chart-when-would-you-build-an-operator-l3"></a>
### 214. Kubernetes Q108: Explain Kubernetes Operator pattern vs Helm chart When would you build an Operator [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Explain Kubernetes Operator pattern vs Helm chart. When would you build an Operator?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Helm chart = templated K8s YAML for stateless deployment. No runtime intelligence. Good for most stateless apps. Operator = custom controller with domain logic. It knows about the application's lifecycle and handles complex operational tasks: automated backups, failover, rolling upgrades with application-level validation, auto-scaling based on app-specific metrics. Build an operator when: your app has complex stateful operations, you need automated operational tasks, or you're building a platform component that other teams will consume (like a database operator). Don't build one for simple stateless apps — Helm is simpler.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Helm chart = templated K8s YAML for stateless deployment. No runtime intelligence. Good for most stateless apps..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Helm chart = templated K8s YAML for stateless deployment. No runtime intelligence. Good for mos
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-215-kubernetes-q109-how-do-you-do-a-canary-deployment-on-kubernetes-without-a-service-mesh-l2"></a>
### 215. Kubernetes Q109: How do you do a canary deployment on Kubernetes without a service mesh [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you do a canary deployment on Kubernetes without a service mesh?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Use two Deployments with the same Service label selector but different replica counts:

- `app-stable`: 9 replicas, version v1
- `app-canary`: 1 replica, version v2

##### 2️⃣ Remediation & Permanent Safeguards

The Service routes to all pods matching `app: myapp`. Traffic split ≈ 90%/10% based on replica ratio. Pros: simple, no extra tools. Cons: rough traffic split (not exact percentage), all users might hit canary randomly. For precise splits, use Argo Rollouts or Flagger.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: app-stable: 9 replicas, version v1.

#### ⏱️ 60-Second Elevator Pitch Summary

- app-stable: 9 replicas, version v1
- app-canary: 1 replica, version v2

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-216-kubernetes-q110-what-is-the-purpose-of-the-kube-proxy-and-what-happens-if-it-goes-down-l3"></a>
### 216. Kubernetes Q110: What is the purpose of the kube-proxy and what happens if it goes down [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is the purpose of the `kube-proxy` and what happens if it goes down?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

kube-proxy runs on every node (as a DaemonSet) and maintains network rules (iptables or ipvs) that implement Services. It watches the API server for Service/Endpoint changes and updates the rules.

- Existing connections continue (iptables rules still exist).
- New Service/Endpoint changes won't be applied on that node.
- New pods that need to reach a new Service may fail.

##### 2️⃣ Remediation & Permanent Safeguards

If kube-proxy goes down on a node: Recovery: restart the kube-proxy pod. It re-syncs all rules.

- Pods on that node may route to removed pods.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Existing connections continue (iptables rules still exist)..

#### ⏱️ 60-Second Elevator Pitch Summary

- Existing connections continue (iptables rules still exist).
- New Service/Endpoint changes won't be applied on that node.
- New pods that need to reach a new Service may fail.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-217-kubernetes-q111-how-do-you-share-a-single-nginx-config-across-multiple-pods-l2"></a>
### 217. Kubernetes Q111: How do you share a single Nginx config across multiple pods [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you share a single Nginx config across multiple pods?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Store the nginx.conf in a ConfigMap. Mount it as a volume in the Deployment. All pods get the same config from the same source. When config changes, update the ConfigMap, then trigger a rolling restart (`kubectl rollout restart deployment/`).

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Store the nginx.conf in a ConfigMap. Mount it as a volume in the Deployment. All pods get the same config from the same source. Wh.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Store the nginx.conf in a ConfigMap. Mount it as a volume in the Deployment. All pods get the s
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-218-kubernetes-q112-what-is-pod-topology-spread-constraints-and-how-is-it-different-from-podantiaffinity-l3"></a>
### 218. Kubernetes Q112: What is Pod Topology Spread Constraints and how is it different from podAntiAffinity [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is Pod Topology Spread Constraints and how is it different from `podAntiAffinity`?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Both spread pods across topology domains (nodes, zones). `podAntiAffinity`: binary — either pods can or can't be on the same node. Doesn't control HOW spread out they are. Topology Spread Constraints: specifies `maxSkew` — the maximum difference in pod count between any two topology domains. `maxSkew: 1` means: never have more than 1 extra pod in one zone vs another. More granular control for even distribution. Example: 10 pods across 3 zones. With `maxSkew: 1`: could be 4/3/3. Anti-affinity would just say "no two pods on same node" which doesn't ensure zone balance.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Both spread pods across topology domains (nodes, zones)..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Both spread pods across topology domains (nodes, zones).
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-219-kubernetes-q113-how-do-you-implement-health-checks-for-a-grpc-service-in-kubernetes-l2"></a>
### 219. Kubernetes Q113: How do you implement health checks for a gRPC service in Kubernetes [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you implement health checks for a gRPC service in Kubernetes?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use the gRPC Health Checking Protocol. Your service implements `grpc.health.v1.Health/Check`. In the probe: This is available since K8s 1.24. For older versions: use `exec` probe with `grpc_health_probe` binary copied into the container.

```bash
grpc:
  port: 50051
  service: "myapp"  # optional service name
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use the gRPC Health Checking Protocol. Your service implements grpc.health.v1.Health/Check. In the probe:.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use the gRPC Health Checking Protocol. Your service implements grpc.health.v1.Health/Check. In
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-220-kubernetes-q114-describe-how-kubernetes-implements-services-using-ipvs-mode-instead-of-iptables-l3"></a>
### 220. Kubernetes Q114: Describe how Kubernetes implements Services using IPVS mode instead of iptables [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Describe how Kubernetes implements Services using IPVS mode instead of iptables."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

In iptables mode: kube-proxy creates a chain of iptables rules for each Service. With thousands of Services, rule traversal becomes linear (O(n)). Performance degrades. In IPVS mode: kube-proxy creates an IPVS virtual server for each Service ClusterIP. IPVS uses hash tables for O(1) lookup. Scales to tens of thousands of Services. Also supports more load balancing algorithms: round-robin, least connections, IPIP, etc. Enable: `--proxy-mode=ipvs` in kube-proxy config. Requires `ipvs` kernel modules. Recommended for large clusters.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: In iptables mode: kube-proxy creates a chain of iptables rules for each Service. With thousands of Services, rule traversal become.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: In iptables mode: kube-proxy creates a chain of iptables rules for each Service. With thousands
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-221-kubernetes-q115-you-have-a-kubernetes-cluster-in-two-regions-for-disaster-recovery-how-do-you-sync-workloads-l2"></a>
### 221. Kubernetes Q115: You have a Kubernetes cluster in two regions for disaster recovery How do you sync workloads [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"You have a Kubernetes cluster in two regions for disaster recovery. How do you sync workloads?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use GitOps (ArgoCD) with a shared Git repository. Both clusters sync from the same manifests repo. Each cluster has its own ArgoCD instance. If primary cluster fails: the DR cluster already has all the workload definitions; just ensure the workloads are running (they might be scaled to 0 in DR to save cost, scale them up). For data: use database replication (Aurora Global, DynamoDB Global Tables). For traffic: Route 53 health checks with failover routing. If primary endpoint goes down, Route 53 automatically routes to DR cluster.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use GitOps (ArgoCD) with a shared Git repository. Both clusters sync from the same manifests repo. Each cluster has its own ArgoCD.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use GitOps (ArgoCD) with a shared Git repository. Both clusters sync from the same manifests re
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-222-kubernetes-q116-what-is-the-container-runtime-interface-cri-and-what-runtimes-are-commonly-used-l3"></a>
### 222. Kubernetes Q116: What is the Container Runtime Interface (CRI) and what runtimes are commonly used [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is the Container Runtime Interface (CRI) and what runtimes are commonly used?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

CRI is the API between kubelet and the container runtime. kubelet doesn't care what runtime is used as long as it speaks CRI.

- **containerd** — most popular. Lightweight, CNCF project. Used in EKS, AKS, GKE.
- **CRI-O** — designed specifically for K8s. Used in OpenShift.
- **Docker** (via dockershim) — removed from K8s 1.24. Docker now uses containerd internally anyway.

##### 2️⃣ Remediation & Permanent Safeguards

Common runtimes: The runtime handles: pulling images, creating/stopping containers, managing namespaces. kubelet just calls CRI APIs.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: containerd — most popular. Lightweight, CNCF project. Used in EKS, AKS, GKE..

#### ⏱️ 60-Second Elevator Pitch Summary

- containerd — most popular. Lightweight, CNCF project. Used in EKS, AKS, GKE.
- CRI-O — designed specifically for K8s. Used in OpenShift.
- Docker (via dockershim) — removed from K8s 1.24. Docker now uses containerd internally anyway.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-223-kubernetes-q117-how-do-you-implement-autoscaling-based-on-custom-metrics-eg-queue-depth-l2"></a>
### 223. Kubernetes Q117: How do you implement autoscaling based on custom metrics (eg queue depth) [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you implement autoscaling based on custom metrics (e.g., queue depth)?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use KEDA (Kubernetes Event-Driven Autoscaling). KEDA supports 50+ built-in scalers: This scales the worker deployment based on SQS queue depth — 1 pod per 5 messages. Scales to zero when queue is empty.

```yaml
apiVersion: keda.sh/v1alpha1
kind: ScaledObject
metadata:
  name: worker-scaler
spec:
  scaleTargetRef:
    name: worker-deployment
  triggers:
  - type: aws-sqs-queue
    metadata:
      queueURL: https://sqs.us-east-1.amazonaws.com/123/my-queue
      queueLength: "5"
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use KEDA (Kubernetes Event-Driven Autoscaling). KEDA supports 50+ built-in scalers:.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use KEDA (Kubernetes Event-Driven Autoscaling). KEDA supports 50+ built-in scalers:
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-224-kubernetes-q118-a-pod-is-being-scheduled-and-then-immediately-evicted-whats-happening-l2"></a>
### 224. Kubernetes Q118: A pod is being scheduled and then immediately evicted Whats happening [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"A pod is being scheduled and then immediately evicted. What's happening?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Node is under resource pressure. kubelet evicts lower-priority pods to free resources. Check: `kubectl describe pod ` — reason will say `Evicted` with a reason (memory, disk). Check node conditions: `kubectl describe node ` — MemoryPressure, DiskPressure, PIDPressure. Fix: increase node size, add more nodes, reduce pod resource requests, clean up eviction-causing pressure (disk full, memory leak).

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Node is under resource pressure. kubelet evicts lower-priority pods to free resources. Check: kubectl describe pod  — reason will .

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Node is under resource pressure. kubelet evicts lower-priority pods to free resources. Check: k
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-225-kubernetes-q119-how-do-you-implement-multi-cluster-service-discovery-so-service-a-in-cluster-1-can-call-service-b-in-cluster-2-l3"></a>
### 225. Kubernetes Q119: How do you implement multi-cluster service discovery so Service A in cluster 1 can call Service B in cluster 2 [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you implement multi-cluster service discovery so Service A in cluster 1 can call Service B in cluster 2?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Options:

- **Submariner** — CNCF project. Creates IPsec tunnels between clusters, enables pod-to-pod communication across clusters.
- **Istio multi-cluster** — Istio service mesh spanning multiple clusters with shared control plane or separate control planes with federation.
- **AWS Cloud Map + Route 53** — register services from both clusters in Cloud Map. Use DNS for discovery.

##### 2️⃣ Remediation & Permanent Safeguards

Execute the resolution runbook and verify workload health:

- **External Ingress** — expose Service B via Ingress/NLB in cluster 2. Service A calls it via the external DNS name. Simple but requires internet or VPC peering.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Submariner — CNCF project. Creates IPsec tunnels between clusters, enables pod-to-pod communication across clusters..

#### ⏱️ 60-Second Elevator Pitch Summary

- Submariner — CNCF project. Creates IPsec tunnels between clusters, enables pod-to-pod communicati...
- Istio multi-cluster — Istio service mesh spanning multiple clusters with shared control plane or ...
- AWS Cloud Map + Route 53 — register services from both clusters in Cloud Map. Use DNS for discovery.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-226-kubernetes-q120-what-is-a-pause-container-and-why-is-it-in-every-pod-l2"></a>
### 226. Kubernetes Q120: What is a pause container and why is it in every pod [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is a pause container and why is it in every pod?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

The "infra container" or "sandbox container" that holds the network namespace for the pod. All containers in the pod join its network namespace (that's how they share localhost). If the app container dies and restarts, the network namespace (and IP address) is preserved because the pause container keeps running. Image: `pause:3.x` (few hundred KB). Managed by containerd/CRI-O, not visible in `kubectl get pods`. **Q121-Q150. More Kubernetes Rapid-fire**

#### 🎯 Key Architectural Takeaway
> Pro-Tip: The "infra container" or "sandbox container" that holds the network namespace for the pod. All containers in the pod join its netw.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: The "infra container" or "sandbox container" that holds the network namespace for the pod. All
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-227-kubernetes-q121-what-is-imagepullpolicy-always-vs-ifnotpresent-l2"></a>
### 227. Kubernetes Q121: What is imagePullPolicy Always vs IfNotPresent [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is `imagePullPolicy: Always` vs `IfNotPresent`?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Always: pulls from registry every pod start (ensures latest changes). IfNotPresent: uses local cache if image tag exists. Production: use specific tags + IfNotPresent (predictable). Dev with `latest`: Always (but avoid `latest` in prod).

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Always: pulls from registry every pod start (ensures latest changes). IfNotPresent: uses local cache if image tag exists. Producti.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Always: pulls from registry every pod start (ensures latest changes). IfNotPresent: uses local
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-228-kubernetes-q122-how-do-you-configure-resource-requests-and-limits-for-init-containers-l2"></a>
### 228. Kubernetes Q122: How do you configure resource requests and limits for init containers [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you configure resource requests and limits for init containers?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Same as regular containers under `initContainers[].resources`. Init containers don't run simultaneously, so effective pod request = max(init container requests, sum of app container requests).

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Same as regular containers under initContainers[].resources. Init containers don't run simultaneously, so effective pod request = .

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Same as regular containers under initContainers[].resources. Init containers don't run simultan
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-229-kubernetes-q123-what-is-a-projected-volume-in-kubernetes-l3"></a>
### 229. Kubernetes Q123: What is a projected volume in Kubernetes [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is a projected volume in Kubernetes?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Combines multiple volume sources (secrets, configmaps, serviceAccountToken, downward API) into a single directory mount. Useful when the app expects all config in one place.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Combines multiple volume sources (secrets, configmaps, serviceAccountToken, downward API) into a single directory mount. Useful wh.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Combines multiple volume sources (secrets, configmaps, serviceAccountToken, downward API) into
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-230-kubernetes-q124-how-do-you-check-what-labels-are-on-a-node-l2"></a>
### 230. Kubernetes Q124: How do you check what labels are on a node [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you check what labels are on a node?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`kubectl get node  --show-labels` or `kubectl describe node `. Add labels: `kubectl label node  key=value`.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: kubectl get node  --show-labels or kubectl describe node . Add labels: kubectl label node  key=value..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: kubectl get node  --show-labels or kubectl describe node . Add labels: kubectl label node  key=
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-231-kubernetes-q125-what-is-the-downward-api-in-kubernetes-l2"></a>
### 231. Kubernetes Q125: What is the downward API in Kubernetes [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is the downward API in Kubernetes?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Exposes pod/node metadata (pod name, namespace, labels, annotations, resource limits) to the container as env vars or volume files. Useful for apps that need to know their own pod name or resource limits without calling the API server.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Exposes pod/node metadata (pod name, namespace, labels, annotations, resource limits) to the container as env vars or volume files.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Exposes pod/node metadata (pod name, namespace, labels, annotations, resource limits) to the co
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-232-kubernetes-q126-how-do-you-handle-pod-disruptions-during-kubernetes-version-upgrades-l3"></a>
### 232. Kubernetes Q126: How do you handle pod disruptions during Kubernetes version upgrades [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you handle pod disruptions during Kubernetes version upgrades?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Set PodDisruptionBudgets on all critical workloads. `kubectl drain --ignore-daemonsets --delete-emptydir-data`. The drain respects PDBs — won't proceed if it would violate them. Upgrade one node at a time. Monitor workloads between each node upgrade.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Set PodDisruptionBudgets on all critical workloads. kubectl drain --ignore-daemonsets --delete-emptydir-data. The drain respects P.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Set PodDisruptionBudgets on all critical workloads. kubectl drain --ignore-daemonsets --delete-
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-233-kubernetes-q127-what-is-kubectl-diff-l2"></a>
### 233. Kubernetes Q127: What is kubectl diff [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is `kubectl diff`?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Shows what would change if you applied a manifest, compared to what's currently running. Like `terraform plan` for Kubernetes.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Shows what would change if you applied a manifest, compared to what's currently running. Like terraform plan for Kubernetes..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Shows what would change if you applied a manifest, compared to what's currently running. Like t
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-234-kubernetes-q128-how-do-you-enforce-that-all-pods-in-a-namespace-must-have-resource-limits-l2"></a>
### 234. Kubernetes Q128: How do you enforce that all pods in a namespace must have resource limits [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you enforce that all pods in a namespace must have resource limits?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

LimitRange with `defaultRequest` and `default` limits OR use OPA/Gatekeeper/Kyverno policy that rejects pods without resource limits.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: LimitRange with defaultRequest and default limits OR use OPA/Gatekeeper/Kyverno policy that rejects pods without resource limits..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: LimitRange with defaultRequest and default limits OR use OPA/Gatekeeper/Kyverno policy that rej
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-235-kubernetes-q129-what-is-vertical-pod-autoscaler-vpa-and-when-should-you-use-it-vs-hpa-l3"></a>
### 235. Kubernetes Q129: What is Vertical Pod Autoscaler (VPA) and when should you use it vs HPA [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is Vertical Pod Autoscaler (VPA) and when should you use it vs HPA?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

VPA adjusts CPU/memory requests of running pods based on actual usage. Use VPA for: workloads where you know they need more resources but can't scale horizontally (stateful single replicas). Use HPA for: stateless apps where horizontal scaling makes sense. Don't use both on the same deployment (conflict on CPU metrics).

#### 🎯 Key Architectural Takeaway
> Pro-Tip: VPA adjusts CPU/memory requests of running pods based on actual usage. Use VPA for: workloads where you know they need more resour.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: VPA adjusts CPU/memory requests of running pods based on actual usage. Use VPA for: workloads w
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-236-kubernetes-q130-how-do-you-temporarily-expose-a-service-from-a-remote-cluster-to-your-local-machine-for-debugging-l2"></a>
### 236. Kubernetes Q130: How do you temporarily expose a service from a remote cluster to your local machine for debugging [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you temporarily expose a service from a remote cluster to your local machine for debugging?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`kubectl port-forward service/ 8080:80` — forwards local port 8080 to the service's port 80. Works through the API server tunnel. Kills when you close the terminal.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: kubectl port-forward service/ 8080:80 — forwards local port 8080 to the service's port 80. Works through the API server tunnel. Ki.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: kubectl port-forward service/ 8080:80 — forwards local port 8080 to the service's port 80. Work
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-237-kubernetes-q131-what-is-kubectl-top-and-what-does-it-need-to-work-l2"></a>
### 237. Kubernetes Q131: What is kubectl top and what does it need to work [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is `kubectl top` and what does it need to work?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Shows real-time CPU/memory usage of nodes and pods. Requires metrics-server to be installed. `kubectl top nodes` and `kubectl top pods`.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Shows real-time CPU/memory usage of nodes and pods. Requires metrics-server to be installed. kubectl top nodes and kubectl top pod.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Shows real-time CPU/memory usage of nodes and pods. Requires metrics-server to be installed. ku
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-238-kubernetes-q132-how-does-kubernetes-handle-pod-security-with-the-pod-security-standards-l3"></a>
### 238. Kubernetes Q132: How does Kubernetes handle pod security with the Pod Security Standards [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How does Kubernetes handle pod security with the Pod Security Standards?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Three levels: Privileged (no restrictions), Baseline (blocks most dangerous capabilities — no privileged, no hostPath), Restricted (most secure — non-root, no capabilities, seccomp required). Apply per-namespace with PodSecurityAdmission: `pod-security.kubernetes.io/enforce: restricted` label on the namespace.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Three levels: Privileged (no restrictions), Baseline (blocks most dangerous capabilities — no privileged, no hostPath), Restricted.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Three levels: Privileged (no restrictions), Baseline (blocks most dangerous capabilities — no p
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-239-kubernetes-q133-what-is-a-kubernetes-lease-l2"></a>
### 239. Kubernetes Q133: What is a Kubernetes lease [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is a Kubernetes lease?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Lightweight K8s object used for leader election by control plane components (scheduler, controller-manager) and custom controllers. The holder updates the lease's `renewTime` periodically. If it misses renewal (dies), another candidate takes over by writing its identity to the lease.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Lightweight K8s object used for leader election by control plane components (scheduler, controller-manager) and custom controllers.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Lightweight K8s object used for leader election by control plane components (scheduler, control
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-240-kubernetes-q134-how-do-you-get-events-for-a-specific-namespace-sorted-by-time-l2"></a>
### 240. Kubernetes Q134: How do you get events for a specific namespace sorted by time [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you get events for a specific namespace sorted by time?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`kubectl get events -n  --sort-by='.lastTimestamp'`. Events are a great first stop when debugging — they capture all resource state changes.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: kubectl get events -n  --sort-by='.lastTimestamp'. Events are a great first stop when debugging — they capture all resource state .

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: kubectl get events -n  --sort-by='.lastTimestamp'. Events are a great first stop when debugging
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-241-kubernetes-q135-what-is-a-service-mesh-and-when-is-the-complexity-worth-it-l3"></a>
### 241. Kubernetes Q135: What is a Service Mesh and when is the complexity worth it [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is a Service Mesh and when is the complexity worth it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Service mesh (Istio, Linkerd) adds a sidecar proxy to every pod, enabling: mTLS, traffic policies, retries, circuit breaking, distributed tracing, traffic splitting. Complex to operate. Worth it when: you have 10+ services and need consistent observability across all, you need mTLS for compliance (zero-trust), you want traffic management (canary deployments, circuit breaking) without code changes. Not worth it for: small number of services, team without mesh expertise.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Service mesh (Istio, Linkerd) adds a sidecar proxy to every pod, enabling: mTLS, traffic policies, retries, circuit breaking, dist.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Service mesh (Istio, Linkerd) adds a sidecar proxy to every pod, enabling: mTLS, traffic polici
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-242-kubernetes-q136-how-do-you-forward-all-logs-from-a-kubernetes-pod-to-elasticsearch-l2"></a>
### 242. Kubernetes Q136: How do you forward all logs from a Kubernetes pod to Elasticsearch [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you forward all logs from a Kubernetes pod to Elasticsearch?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use Fluentd or Filebeat as a DaemonSet. They read container logs from `/var/log/containers/` on each node and ship to Elasticsearch. Alternatively: configure your app to log in JSON format to stdout, and the DaemonSet collects and forwards.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use Fluentd or Filebeat as a DaemonSet. They read container logs from /var/log/containers/ on each node and ship to Elasticsearch..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use Fluentd or Filebeat as a DaemonSet. They read container logs from /var/log/containers/ on e
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-243-kubernetes-q137-what-is-ebpf-and-how-is-it-used-in-kubernetes-networking-l3"></a>
### 243. Kubernetes Q137: What is eBPF and how is it used in Kubernetes networking [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is eBPF and how is it used in Kubernetes networking?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Extended Berkeley Packet Filter — runs sandboxed programs in the Linux kernel. In K8s: Cilium uses eBPF instead of iptables for service routing. Benefits: much faster (kernel bypass for Service lookup), better observability (Hubble), network policy at L7. Becoming the modern replacement for iptables-based kube-proxy.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Extended Berkeley Packet Filter — runs sandboxed programs in the Linux kernel. In K8s: Cilium uses eBPF instead of iptables for se.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Extended Berkeley Packet Filter — runs sandboxed programs in the Linux kernel. In K8s: Cilium u
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-244-kubernetes-q138-what-happens-when-you-delete-a-namespace-that-has-resources-in-it-l2"></a>
### 244. Kubernetes Q138: What happens when you delete a namespace that has resources in it [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What happens when you delete a namespace that has resources in it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

K8s deletes all resources in the namespace in dependency order. The namespace stays in `Terminating` until all resources are deleted. If a resource has a finalizer that never gets removed, the namespace is stuck terminating forever. Fix: remove finalizers from stuck resources.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: K8s deletes all resources in the namespace in dependency order. The namespace stays in Terminating until all resources are deleted.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: K8s deletes all resources in the namespace in dependency order. The namespace stays in Terminat
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-245-kubernetes-q139-how-do-you-run-a-pod-on-the-control-plane-node-l2"></a>
### 245. Kubernetes Q139: How do you run a pod on the control plane node [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you run a pod on the control plane node?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Control plane nodes are tainted with `node-role.kubernetes.io/control-plane:NoSchedule`. Add a toleration to your pod: `tolerations: [{key: "node-role.kubernetes.io/control-plane", operator: "Exists"}]`. Or use `nodeSelector` with the control-plane node label.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Control plane nodes are tainted with node-role.kubernetes.io/control-plane:NoSchedule. Add a toleration to your pod: tolerations: .

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Control plane nodes are tainted with node-role.kubernetes.io/control-plane:NoSchedule. Add a to
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-246-kubernetes-q140-explain-kubernetes-network-policies-default-behavior-and-why-it-can-be-a-security-risk-l3"></a>
### 246. Kubernetes Q140: Explain Kubernetes Network Policies default behavior and why it can be a security risk [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"Explain Kubernetes Network Policies' default behavior and why it can be a security risk."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

By default, K8s has NO network isolation. All pods can talk to all other pods in the cluster, across namespaces. This is intentional (for ease of use) but dangerous in multi-tenant clusters. A pod in namespace A can directly reach a DB pod in namespace B if it knows the IP. Fix: create a "default deny all" NetworkPolicy in every namespace, then explicitly allow required traffic. This is the secure-by-default approach.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: By default, K8s has NO network isolation. All pods can talk to all other pods in the cluster, across namespaces. This is intention.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: By default, K8s has NO network isolation. All pods can talk to all other pods in the cluster, a
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-247-kubernetes-q141-what-is-a-sidecar-container-pattern-l2"></a>
### 247. Kubernetes Q141: What is a sidecar container pattern [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is a sidecar container pattern?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

A helper container that runs alongside the main app container in the same pod, sharing its network and volumes. Examples: Istio proxy (Envoy), Fluentd for log shipping, Vault agent for secrets, nginx as SSL terminator. The sidecar handles cross-cutting concerns without modifying the main app.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: A helper container that runs alongside the main app container in the same pod, sharing its network and volumes. Examples: Istio pr.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: A helper container that runs alongside the main app container in the same pod, sharing its netw
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-248-kubernetes-q142-how-do-you-pass-the-pods-own-name-to-the-app-running-inside-it-l2"></a>
### 248. Kubernetes Q142: How do you pass the pods own name to the app running inside it [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you pass the pod's own name to the app running inside it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use downward API:

```bash
env:
- name: POD_NAME
  valueFrom:
    fieldRef:
      fieldPath: metadata.name
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use downward API:.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use downward API:
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-249-kubernetes-q143-what-is-kubernetes-federation-and-is-it-still-recommended-l3"></a>
### 249. Kubernetes Q143: What is Kubernetes Federation and is it still recommended [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is Kubernetes Federation and is it still recommended?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Federation v1 (deprecated) tried to manage multiple clusters from a single control plane. It was complex and unreliable. Federation v2 (KubeFed) also proved difficult. Current recommendation: use GitOps (ArgoCD multi-cluster) or dedicated tools (Rancher, Anthos) for multi-cluster management instead.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Federation v1 (deprecated) tried to manage multiple clusters from a single control plane. It was complex and unreliable. Federatio.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Federation v1 (deprecated) tried to manage multiple clusters from a single control plane. It wa
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-250-kubernetes-q144-how-do-you-create-a-self-signed-tls-certificate-for-an-ingress-l2"></a>
### 250. Kubernetes Q144: How do you create a self-signed TLS certificate for an Ingress [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you create a self-signed TLS certificate for an Ingress?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use cert-manager with `ClusterIssuer: selfsigned`. Or: `openssl req -x509 -nodes -newkey rsa:2048 -out tls.crt -keyout tls.key`, then `kubectl create secret tls my-tls --cert=tls.crt --key=tls.key`. Reference in Ingress `tls` section.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use cert-manager with ClusterIssuer: selfsigned. Or: openssl req -x509 -nodes -newkey rsa:2048 -out tls.crt -keyout tls.key, then .

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use cert-manager with ClusterIssuer: selfsigned. Or: openssl req -x509 -nodes -newkey rsa:2048
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-251-kubernetes-q145-what-is-an-admission-controller-and-how-does-kubernetes-use-them-l3"></a>
### 251. Kubernetes Q145: What is an Admission Controller and how does Kubernetes use them [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is an Admission Controller and how does Kubernetes use them?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Plugins that intercept API requests AFTER authentication/authorization but BEFORE persistence in etcd. Two types: Mutating (modify the resource) and Validating (accept/reject). Built-in examples: NamespaceLifecycle (rejects resources in terminating namespaces), ResourceQuota (rejects resources that exceed quota), LimitRanger (sets default limits). Custom ones use webhook admission.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Plugins that intercept API requests AFTER authentication/authorization but BEFORE persistence in etcd. Two types: Mutating (modify.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Plugins that intercept API requests AFTER authentication/authorization but BEFORE persistence i
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-252-kubernetes-q146-how-do-you-retrieve-only-the-logs-from-a-specific-container-in-a-pod-that-has-multiple-containers-l2"></a>
### 252. Kubernetes Q146: How do you retrieve only the logs from a specific container in a pod that has multiple containers [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you retrieve only the logs from a specific container in a pod that has multiple containers?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`kubectl logs  -c `. Get container names: `kubectl get pod  -o jsonpath='{.spec.containers[*].name}'`.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: kubectl logs  -c . Get container names: kubectl get pod  -o jsonpath='{.spec.containers[*].name}'..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: kubectl logs  -c . Get container names: kubectl get pod  -o jsonpath='{.spec.containers[].name}
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-253-kubernetes-q147-what-is-kubectl-apply-prune-l2"></a>
### 253. Kubernetes Q147: What is kubectl apply --prune [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is `kubectl apply --prune`?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

When combined with a label selector, it deletes resources that were previously applied with `kubectl apply` but are no longer in the current manifest set. Useful for GitOps without a full GitOps controller — cleans up old resources.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: When combined with a label selector, it deletes resources that were previously applied with kubectl apply but are no longer in the.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: When combined with a label selector, it deletes resources that were previously applied with kub
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-254-kubernetes-q148-how-do-you-implement-an-egress-gateway-in-a-kubernetes-cluster-l3"></a>
### 254. Kubernetes Q148: How do you implement an egress gateway in a Kubernetes cluster [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you implement an egress gateway in a Kubernetes cluster?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Kubernetes is a declarative desired state system; understanding the reconciliation loop is how you diagnose this quickly. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Force all outbound traffic through a central point (useful for IP whitelisting at third-party APIs). With Istio: configure an EgressGateway service and VirtualService/DestinationRule to route external traffic through it. The gateway's pod IPs can be given static Elastic IPs on AWS. All external traffic appears from known IPs.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Force all outbound traffic through a central point (useful for IP whitelisting at third-party APIs). With Istio: configure an Egre.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Force all outbound traffic through a central point (useful for IP whitelisting at third-party A
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-255-kubernetes-q149-what-is-the-significance-of-the-dry-run-server-flag-vs-dry-run-client-l2"></a>
### 255. Kubernetes Q149: What is the significance of the --dry-run=server flag vs --dry-run=client [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"What is the significance of the `--dry-run=server` flag vs `--dry-run=client`?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our production Kubernetes clusters running microservices on EKS/AKS, this was a classic operational challenge. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

`client`: validates locally using the cached schema. `server`: sends to the API server which validates (including webhook admission controllers) without persisting. Server-side dry-run is more accurate — catches webhook validation issues that client-side misses.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: client: validates locally using the cached schema. server: sends to the API server which validates (including webhook admission co.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: client: validates locally using the cached schema. server: sends to the API server which valida
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-256-kubernetes-q150-how-do-you-implement-a-global-rate-limiter-for-all-requests-to-your-services-in-kubernetes-l3"></a>
### 256. Kubernetes Q150: How do you implement a global rate limiter for all requests to your services in Kubernetes [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you implement a global rate limiter for all requests to your services in Kubernetes?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

With Istio: EnvoyFilter or RateLimitPolicy using a Redis-backed rate limit service. With nginx-ingress: `nginx.ingress.kubernetes.io/limit-rps` annotation. With Envoy-based Ingress: global rate limiting service (Envoy Rate Limit) shared across all ingress instances for true global limits.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: With Istio: EnvoyFilter or RateLimitPolicy using a Redis-backed rate limit service. With nginx-ingress: nginx.ingress.kubernetes.i.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: With Istio: EnvoyFilter or RateLimitPolicy using a Redis-backed rate limit service. With nginx-
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-257-multi-cloud-docker-workload-architecture-build-once-deploy-portably"></a>
### 257. Multi-Cloud Docker Workload Architecture: Build Once, Deploy Portably

**Level:** `Senior DevOps / SRE` | **Category:** `Docker` • `Docker in CI/CD` | **Type:** `CI/CD Architecture`

**Tags:** `Docker` `Multi-Cloud` `Buildx` `EKS` `AKS`

> **Interview Question:**  
> *"How would you manage Docker workloads across multiple clouds (e.g., AWS and Azure)?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
I avoid managing raw Docker hosts manually across clouds. Instead, I standardize on immutable, multi-architecture images built once via Buildx, push them to a central registry strategy (such as GHCR or replicated ECR/ACR), and run workloads on managed Kubernetes orchestrators (EKS, AKS, GKE). Deployment is driven by Terraform and GitHub Actions with environment parity, shared Helm charts, and cloud-specific values overlays.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Immutable Multi-Architecture Builds & Registry Distribution

Ensure container images execute seamlessly across cloud providers and CPU architectures (AMD64/ARM64):

- **Docker Buildx:** Build multi-platform images (`linux/amd64`, `linux/arm64`) using Docker BuildKit to support diverse cloud VM instances.
- **Centralized vs Replicated Registry:** Store images in a global registry (GHCR/JFrog) or replicate automatically to regional cloud registries (AWS ECR / Azure ACR) to avoid cross-cloud egress costs and rate limits.
- **Strict Semantic Digest Tagging:** Deploy using immutable tags or SHA256 digests to guarantee binary parity across cloud environments.

```bash
# Create and use multi-architecture buildx builder
docker buildx create --use --name multi || true

# Build and push multi-arch image
docker buildx build --platform linux/amd64,linux/arm64 \
  -t ghcr.io/org/api:1.8.0 -t ghcr.io/org/api:latest --push .

# Replicate to cloud-specific registry if required
docker pull ghcr.io/org/api:1.8.0
docker tag ghcr.io/org/api:1.8.0 <aws_account>.dkr.ecr.ap-south-1.amazonaws.com/api:1.8.0
docker push <aws_account>.dkr.ecr.ap-south-1.amazonaws.com/api:1.8.0
```

##### 2️⃣ Unified Orchestration & Cloud Abstraction Layer

Decouple application code and container configuration from cloud-specific infrastructure services:

- **Standardized Kubernetes Orchestration:** Run workloads on EKS and AKS using identical core manifest definitions rather than raw VM Docker daemons.
- **Base Chart with Cloud Overlays:** Use a shared Helm chart for the microservice with cloud-specific `values-aws.yaml` and `values-azure.yaml` (e.g., storage classes, ingress annotations).
- **Terraform Infrastructure Modules:** Abstract cloud primitives (VPC, IAM, Managed DB) behind modular Terraform modules while keeping application deployment pipelines identical.

```bash
# Deploy identical chart with cloud-specific values overlay
# AWS deployment:
helm upgrade --install api charts/api -f values.yaml -f values-aws.yaml

# Azure deployment:
helm upgrade --install api charts/api -f values.yaml -f values-azure.yaml
```

#### 🎯 Key Architectural Takeaway
> Achieve multi-cloud container portability by building multi-arch images once in CI, using a unified orchestrator (Kubernetes on EKS/AKS), and isolating cloud differences into Terraform and Helm values overlays.

#### ⏱️ 60-Second Elevator Pitch Summary

- Build immutable multi-architecture container images once using Docker Buildx and distribute via central or replicated registries.
- Deploy across clouds using managed Kubernetes (EKS/AKS) to maintain API and runtime parity.
- Use shared Helm charts with cloud-specific values overlays and modular Terraform to abstract cloud infrastructure differences.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-258-production-container-performance-resource-monitoring-architecture"></a>
### 258. Production Container Performance & Resource Monitoring Architecture

**Level:** `Senior DevOps / SRE` | **Category:** `Docker` • `Performance & Troubleshooting` | **Type:** `Technical Deep-Dive`

**Tags:** `Docker` `cgroups` `cAdvisor` `Prometheus` `Grafana`

> **Interview Question:**  
> *"How do you monitor container performance in production?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
I use layered observability: container and host metrics (CPU, memory, filesystem, cgroup throttling), application performance metrics (latency, error rate, throughput), logs, and distributed traces. In Kubernetes, Prometheus, Grafana, and Alertmanager with cAdvisor are standard; for standalone Docker hosts, I use cAdvisor and node-exporter alongside centralized log shipping. I focus alerts on SLO breaches and container throttling rather than noisy raw utilization thresholds.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Fast CLI Diagnostics on Container Hosts

Immediate command-line triage when diagnosing container slowdowns on a live host:

- **Live Resource Streaming:** Run `docker stats` for real-time CPU %, memory usage, limits, and network I/O.
- **Inspect Container State & OOM:** Check container exit codes and OOMKilled state flags with `docker inspect`.
- **Container Events:** Stream recent container lifecycle events (die, oom, kill) with `docker events`.

```bash
# Real-time resource usage stream across running containers
docker stats --no-stream

# Inspect OOM status and termination details
docker inspect <container_id> --format '{{json .State}}' | jq

# Stream container lifecycle events from the last 30 minutes
docker events --since 30m
```

##### 2️⃣ cgroup Throttling & Prometheus Metrics Architecture

Monitor kernel-level cgroup metrics to catch subtle CPU starvation and memory saturation:

- **cAdvisor & Prometheus:** cAdvisor scrapes container cgroup data directly from `/sys/fs/cgroup` and exposes metrics for Prometheus.
- **CPU CFS Throttling:** Monitor `container_cpu_cfs_throttled_seconds_total`. When CPU limits are too tight, the CFS scheduler throttles threads, spiking tail latency even if CPU % looks low.
- **Memory Working Set:** Alert on `container_memory_working_set_bytes` approaching container limits, as this is the exact metric the Linux kernel uses to trigger OOMKills.
- **SLO-Driven Alerts:** Alert when p95/p99 latency degrades or when containers restart repeatedly, rather than alerting on arbitrary CPU utilization.

```bash
# Prometheus Query Examples:
# 1. Detect CFS CPU Throttling Rate (indicates undersized CPU limits):
# rate(container_cpu_cfs_throttled_seconds_total[5m]) > 0.2

# 2. Container Memory Working Set vs Limit (OOM risk):
# sum(container_memory_working_set_bytes) by (pod) / sum(container_spec_memory_limit_bytes) by (pod) > 0.85

# Live Kubernetes cluster checks
kubectl top pods -A
kubectl top nodes
```

#### 🎯 Key Architectural Takeaway
> Monitor CFS CPU throttling (container_cpu_cfs_throttled_seconds_total) and memory working set rather than simple CPU averages. CPU throttling causes severe latency spikes long before a container crashes.

#### ⏱️ 60-Second Elevator Pitch Summary

- Implement layered monitoring: cAdvisor/node-exporter for cgroups, Prometheus/Grafana for metrics, and centralized tracing.
- Track critical cgroup metrics: CFS CPU throttling rate and memory working set to prevent silent latency degradation and OOMKills.
- Configure alerting around user-impacting Golden Signals (latency, errors, saturation) rather than static host thresholds.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-259-live-coding-scenario-writing-an-optimized-secure-multi-stage-dockerfile"></a>
### 259. Live Coding Scenario: Writing an Optimized, Secure Multi-Stage Dockerfile

**Level:** `Senior DevOps / SRE` | **Category:** `Docker` • `Performance & Troubleshooting` | **Type:** `Live Coding Scenario`

**Tags:** `Docker` `Dockerfile` `Multi-Stage` `Security` `Non-Root`

> **Interview Question:**  
> *"Write an optimized, secure multi-stage Dockerfile for a production web service during screen sharing."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
When asked to write a Dockerfile in a live coding interview, I structure it using multi-stage builds to keep the final image minimal, secure, and reproducible. I isolate dependency caching, keep compilers and package managers out of the runtime image, and run the container as an unprivileged non-root user with pinned alpine or distroless base images.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production-Grade Multi-Stage Dockerfile Implementation

Walk the interviewer through each stage: dependency resolution, build stage, and hardened unprivileged runtime:

- **Stage 1 (deps):** Copies package manifests and runs `npm ci` to leverage Docker layer caching when source code changes.
- **Stage 2 (build):** Compiles TypeScript/assets and strips development dependencies with `npm prune --omit=dev`.
- **Stage 3 (runtime):** Uses a lean base image, copies only the compiled output and production modules, sets `NODE_ENV=production`, and runs as non-root user `node`.

```bash
# syntax=docker/dockerfile:1

# Stage 1: Install dependencies
FROM node:20-alpine AS deps
WORKDIR /app
COPY package*.json ./
RUN npm ci

# Stage 2: Build application
FROM node:20-alpine AS build
WORKDIR /app
COPY --from=deps /app/node_modules ./node_modules
COPY . .
RUN npm run build && npm prune --omit=dev

# Stage 3: Minimal production runtime
FROM node:20-alpine AS runtime
WORKDIR /app
ENV NODE_ENV=production
COPY --from=build /app/package*.json ./
COPY --from=build /app/node_modules ./node_modules
COPY --from=build /app/dist ./dist

# Security: Run as unprivileged non-root user
USER node
EXPOSE 3000
CMD ["node", "dist/server.js"]
```

##### 2️⃣ Building, Verification & Security Best Practices

Demonstrate how you verify and test the built container image during the interview:

- **Image Size Comparison:** Compare the multi-stage image (~80MB) against a single-stage image (>1GB).
- **Non-Root Verification:** Execute `id` inside the container to prove it runs as UID 1000 rather than root.
- **Security Hardening:** Highlight the inclusion of a `.dockerignore` file to prevent leaking `.git`, local `node_modules`, and secrets into the image build context.

```bash
# Build and tag the multi-stage image
docker build -t sample-api:multi .

# Verify image size reduction
docker images | grep sample-api

# Run and verify unprivileged execution
docker run --rm -p 3000:3000 sample-api:multi

# Verify running user is non-root
docker run --rm sample-api:multi whoami
```

#### 🎯 Key Architectural Takeaway
> In live coding interviews, articulate why each layer exists: cache package manifests first to speed up rebuilds, prune devDependencies before the final stage, copy only compiled artifacts, and always enforce a non-root USER.

#### ⏱️ 60-Second Elevator Pitch Summary

- Structure the Dockerfile into distinct stages: dependency caching, building/pruning, and minimal unprivileged runtime.
- Leverage layer caching by copying package manifests before application code to avoid re-downloading modules on every commit.
- Harden security by running as a non-root user (USER node / UID 10001) and excluding build tools, test files, and package caches from the final image.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-260-integrating-jenkins-with-docker-kubernetes-and-aws-ecr-eks-for-cloud-native-ci-cd"></a>
### 260. Integrating Jenkins with Docker, Kubernetes, and AWS (ECR/EKS) for Cloud-Native CI/CD

**Level:** `Senior DevOps / SRE` | **Category:** `CI/CD` • `Jenkins & Pipeline Configuration` | **Type:** `CI/CD Architecture`

**Tags:** `CI/CD` `Jenkins` `Docker` `Kubernetes` `Amazon EKS`

> **Interview Question:**  
> *"How did you integrate Jenkins with Docker, Kubernetes, and AWS?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
I integrate Jenkins into the cloud-native ecosystem using three pillars: (1) Docker BuildKit/buildx for multi-architecture image compilation, (2) the Jenkins Kubernetes plugin to provision ephemeral container agents dynamically on EKS, and (3) AWS IAM role assumption via IRSA/OIDC for passwordless authentication to ECR and EKS. Artifacts are versioned by git commit SHA and promoted through environments using Helm.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Dynamic Kubernetes Agent Provisioning & Docker BuildKit

Configure Jenkins to scale build worker pods automatically in response to job queues:

- **Kubernetes Cloud Plugin:** Jenkins Master communicates with the internal K8s API server, spinning up multi-container agent pods with Kaniko or Docker-in-Docker sidecars on demand.
- **BuildKit Layer Caching:** Use Docker Buildx with remote inline cache or AWS ECR cache backends to avoid rebuilding unchanged dependencies.
- **Commit SHA Tagging:** Images are tagged with the immutable short git commit SHA (e.g., `app:abc1234`) rather than mutable tags like `latest`.

```yaml
// Declarative Jenkinsfile pipeline snippet
pipeline {
  agent {
    kubernetes {
      yaml '''
apiVersion: v1
kind: Pod
spec:
  serviceAccountName: jenkins-ecr-deployer
  containers:
  - name: kaniko
    image: gcr.io/kaniko-project/executor:debug
    command: ['sleep', '9999999']
'''
    }
  }
  stages {
    stage('Build & Push') {
      steps {
        sh '/kaniko/executor --context=dir://. --destination=123456789012.dkr.ecr.ap-south-1.amazonaws.com/api:${GIT_COMMIT:0:7}'
      }
    }
  }
}
```

##### 2️⃣ Passwordless ECR/EKS Authentication (IRSA) & Helm Release

Eliminate static AWS keys and deploy declarative workloads to EKS:

- **AWS IRSA (IAM Roles for Service Accounts):** Bind the Jenkins agent ServiceAccount to an AWS IAM Role with strictly scoped permissions for `ecr:PutImage` and EKS access.
- **Staging Automated Deployment:** Automatically trigger `helm upgrade --install` against staging EKS using values overlays.
- **Production Promotion Gate:** Gated with a manual approval stage, canary traffic routing, and automated rollback if HTTP 5xx errors spike.

```bash
# Jenkins deploying to EKS via Helm
aws eks update-kubeconfig --name prod-cluster --region ap-south-1
helm upgrade --install payment-api charts/payment-api \
  -n payments \
  --set image.tag=${GIT_COMMIT:0:7} \
  -f values-prod.yaml \
  --atomic --timeout 5m
```

#### 🎯 Key Architectural Takeaway
> Integrate Jenkins with Kubernetes using dynamic agent pod scaling, build immutable images tagged by git SHA, authenticate to AWS without static keys using IRSA, and release via Helm with --atomic flags.

#### ⏱️ 60-Second Elevator Pitch Summary

- Use the Kubernetes plugin to dynamically schedule single-use ephemeral agent pods on EKS.
- Build immutable container images tagged with git commit SHAs using BuildKit/Kaniko for speed and security.
- Authenticate seamlessly to AWS ECR and EKS using IRSA and deploy versioned Helm charts with automated rollback gates.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-261-why-docker-in-production-eliminating-snowflake-environments-configuration-drift"></a>
### 261. Why Docker in Production: Eliminating Snowflake Environments & Configuration Drift

**Level:** `Senior DevOps / SRE` | **Category:** `Docker` • `Docker` | **Type:** `Core Fundamentals`

**Tags:** `Docker` `Containerization` `Environment Drift` `Immutability` `SRE`

> **Interview Question:**  
> *"What real production problems did Docker solve in your environment?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
Docker solved three fundamental production challenges in our environment: environment drift ('works on my machine'), inconsistent packaging, and slow, fragile release rollbacks. Before containerization, VMs became snowflake servers where OS libraries, Python/Node runtimes, and system configurations diverged over time. Docker allowed us to package application code with its exact runtime dependencies into an immutable artifact tested identically in CI, staging, and production.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Eliminating Snowflake Servers & Parity Across Environments

Overcoming runtime mismatches and configuration discrepancies:

- **Immutable Artifacts:** Packaging the OS userspace, system libraries (e.g. OpenSSL, glibc), and language runtimes into an immutable image ensures dev/prod parity.
- **Zero Host Pollution:** Applications run isolated in Linux namespaces and cgroups without mutating host OS packages, eliminating dependency conflicts between different services on the same VM.
- **Fast Onboarding:** New engineers spin up the entire microservice ecosystem with a single command (`docker compose up`) rather than spending days debugging local runtime dependencies.

```bash
# Inspecting container image immutability and exact OS digest
docker image inspect my-service:1.4.0 --format '{{.Os}}/{{.Architecture}} | Created: {{.Created}}'

# Checking layer history and deterministic packaging
docker history my-service:1.4.0
```

##### 2️⃣ Deployment Velocity, Density & Deterministic Rollbacks

Improving deployment reliability and resource efficiency:

- **Sub-Second Starts:** Containers start in seconds by sharing the host Linux kernel, enabling aggressive auto-scaling compared to 5-10 minute VM boot times.
- **Deterministic Rollbacks:** If a release introduces a bug, rolling back means simply repointing traffic to the previous image tag or digest, which is already cached on the host nodes.
- **Resource Density & FinOps:** Multiple isolated containers pack tightly onto shared worker nodes, maximizing CPU/RAM utilization and cutting cloud infrastructure spend by over 35%.

```bash
# Deterministic rollback is instant because the previous image is already cached
kubectl set image deployment/api api=123456789012.dkr.ecr.ap-south-1.amazonaws.com/api:v1.3.9 -n prod
kubectl rollout status deployment/api -n prod
```

#### 🎯 Key Architectural Takeaway
> Docker replaces fragile snowflake VMs with immutable, portable artifacts. It ensures that the exact binary, libraries, and runtime tested in CI are what runs in production, making rollbacks fast, predictable, and risk-free.

#### ⏱️ 60-Second Elevator Pitch Summary

- Eliminate 'works on my machine' drift by bundling code and system dependencies into immutable container images.
- Accelerate developer onboarding and local testing through reproducible Docker Compose environments.
- Guarantee instant, deterministic production rollbacks by repointing to pre-tested, cached container images.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

<a id="scenario-262-container-image-security-aws-ecr-governance-vulnerability-scanning-signing-lifecycle"></a>
### 262. Container Image Security & AWS ECR Governance: Vulnerability Scanning, Signing & Lifecycle

**Level:** `Senior DevOps / SRE` | **Category:** `Docker` • `Docker in CI/CD` | **Type:** `Technical Deep-Dive`

**Tags:** `Docker` `AWS ECR` `Security` `Trivy` `Cosign`

> **Interview Question:**  
> *"How do you handle container image security and AWS ECR repository management?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
I enforce container security using a shift-left approach combined with registry governance: CI vulnerability scanning with Trivy/Grype, blocking critical CVEs before push, cryptographic signing with Cosign, and AWS ECR repository guardrails. In ECR, I enable Enhanced or Basic scan-on-push, enforce tag immutability to prevent overwriting production tags, configure lifecycle policies to purge untagged images, and restrict access using least-privilege IAM policies.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ CI/CD Scanning with Trivy & Cryptographic Signing with Cosign

Block vulnerabilities before images ever reach the container registry:

- **Automated Trivy Scan:** Scan the built container image in CI, setting `--exit-code 1 --severity CRITICAL,HIGH` to fail pipeline builds on unpatched vulnerabilities.
- **Cryptographic Image Signing:** Use Sigstore Cosign with AWS KMS or OIDC keyless signing to attach a digital signature to the image manifest in ECR.
- **Admission Enforcement:** Deploy Kyverno or OPA Gatekeeper in Kubernetes to reject any pod whose image lacks a verified Cosign signature.

```bash
# Scan image for critical CVEs in CI pipeline
trivy image --exit-code 1 --severity CRITICAL,HIGH \
  --ignore-unfixed 123456789012.dkr.ecr.ap-south-1.amazonaws.com/api:v1.4.0

# Cryptographically sign the image using Cosign and AWS KMS
cosign sign --key awskms:///arn:aws:kms:ap-south-1:123456789012:key/cosign-key \
  123456789012.dkr.ecr.ap-south-1.amazonaws.com/api:v1.4.0
```

##### 2️⃣ AWS ECR Tag Immutability, KMS Encryption & Lifecycle Policies

Enforce repository hygiene, data protection, and storage cost controls in AWS ECR:

- **Tag Immutability:** Enable immutable tags on production repositories so existing release tags cannot be overwritten by subsequent builds.
- **KMS Customer Managed Encryption:** Encrypt repositories using AWS KMS customer managed keys (CMKs) to satisfy compliance mandates.
- **Lifecycle Rules:** Configure automated JSON lifecycle policies to expire untagged images after 3 days and retain only the last 30 tagged production images to eliminate storage bloat.
- **Scan on Push:** Enable continuous vulnerability assessment in ECR to monitor for newly disclosed zero-day vulnerabilities in deployed images.

```bash
# Create ECR repository with Tag Immutability and KMS encryption
aws ecr create-repository --repository-name payment-api \
  --image-tag-mutability IMMUTABLE \
  --encryption-configuration encryptionType=KMS,kmsKey=arn:aws:kms:ap-south-1:123456789012:key/ecr-key \
  --image-scanning-configuration scanOnPush=true

# Apply lifecycle policy to expire untagged images after 3 days
aws ecr put-lifecycle-policy --repository-name payment-api \
  --lifecycle-policy-text '{
    "rules": [
      {"rulePriority": 1, "description": "Expire untagged images", "selection": {"tagStatus": "untagged", "countType": "sinceImagePushed", "countUnit": "days", "countNumber": 3}, "action": {"type": "expire"}},
      {"rulePriority": 2, "description": "Keep last 30 tagged", "selection": {"tagStatus": "any", "countType": "imageCountMoreThan", "countNumber": 30}, "action": {"type": "expire"}}
    ]
  }'
```

#### 🎯 Key Architectural Takeaway
> Shift security left by failing builds on critical CVEs with Trivy, sign images with Cosign, and protect AWS ECR with Tag Immutability, KMS CMKs, and automated lifecycle policies to prevent storage sprawl.

#### ⏱️ 60-Second Elevator Pitch Summary

- Block unpatched vulnerabilities in CI by scanning images with Trivy and signing manifests with Cosign.
- Enforce Tag Immutability and Scan on Push in AWS ECR to guarantee release tamper-proofing.
- Automate repository cost management using ECR lifecycle rules that expire untagged intermediate layers.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=docker)

</details>

---

## 🤝 Contributing & Community

Have an alternative battle-tested runbook or an edge-case to add? PRs and scenario submissions are warmly welcomed!

1. Fork this repository
2. Create a feature branch (`git checkout -b feature/new-runbook`)
3. Commit your changes (`git commit -m 'Add production triage runbook'`)
4. Push to branch (`git push origin feature/new-runbook`)
5. Open a Pull Request

---

### 🔗 Connect with Naveed Ahmed
- 🌐 **Portfolio & Systems:** [naveedkumbhar.com](https://naveedkumbhar.com)
- ✍️ **Tech Blog:** [blog.naveedkumbhar.com](https://blog.naveedkumbhar.com)
- 💼 **LinkedIn:** [linkedin.com/in/naveedkumbhar](https://pk.linkedin.com/in/naveedkumbhar)
- 🐦 **X (Twitter):** [@naveedkumbhar](https://x.com/naveedkumbhar)
- 🧵 **Threads:** [@naveedkumbhar](https://threads.net/@naveedkumbhar)
- 📸 **Instagram:** [@naveedkumbhar](https://instagram.com/naveedkumbhar)
- 📘 **Facebook:** [KiLL3rMiNd](https://www.facebook.com/KiLL3rMiNd)
- 💬 **WhatsApp Direct:** [@naveedkumbhar](https://wa.me/naveedkumbhar)
- 🐙 **GitHub:** [github.com/naveedkumbhar](https://github.com/naveedkumbhar)


---

## 📜 License

This repository is open-source and released under the [MIT License](LICENSE).  

Copyright © 2026 [Naveed Ahmed](https://naveedkumbhar.com). All rights reserved.
