# AgentBase Premium on AWS

AgentBase Premium is our AWS AMI offering that allows custom branding and is one-click deployable to your AWS VPC as an EC2. Head to [AWS Marketplace](https://aws.amazon.com/marketplace/pp/prodview-t22mebxzwjhu6) to subscribe. It's useful in a couple of scenarios:

* You're looking to create one or a few applications as a small/medium business and you care about data residency.
* You are interested in [AgentBase Cloud](cloud.md), but your use case require more resource than supported by the [plans](https://agentbase.ai/pricing).
* You'd like to run a POC before adopting AgentBase Enterprise within your organization.

### Setup

If this is your first time accessing AgentBase, enter the Admin initialization password (set to your EC2's instance ID) to start the set up process.

After the AMI is deployed, access AgentBase via the instance's public IP found in th EC2 console (HTTP port 80 is used by default).

### Upgrading&#x20;

In the EC2 instance, run the following commands:&#x20;

```
git clone https://github.com/agent-base/agentbase.git /tmp/agentbase
mv -f /tmp/agentbase/docker/* /agentbase/
rm -rf /tmp/agentbase
docker-compose down
docker-compose pull
docker-compose -f docker-compose.yaml -f docker-compose.override.yaml up -d
```

### Customizing

Just like self-hosted deploy, you may moagentbase the environment variables under `.env` in your EC2 instance as you see fit. Then, restart AgentBase with:

```
docker-compose down
ocker-compose -f docker-compose.yaml -f docker-compose.override.yaml up -d
```
