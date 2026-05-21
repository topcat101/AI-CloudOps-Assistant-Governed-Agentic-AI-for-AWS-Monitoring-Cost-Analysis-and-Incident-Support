Project idea: Secure Agentic AI Operations Platform

Build an internal AI assistant that helps cloud/platform teams investigate issues, understand AWS costs, query documentation, and recommend safe remediation steps.

It should not just be a chatbot. It should look like a governed internal AI system.

1. Add an AI agent backend

Use Python + FastAPI to build an API backend.

The agent could answer questions like:

“Why did CloudWatch costs increase last month?”
“Which AWS account has the highest cost increase?”
“Summarise this Grafana alert.”
“What runbook should I follow for this incident?”
“What AWS services are causing the biggest spend?”

This helps you show backend engineering, AI integration, API design, and business problem solving.

Suggested stack:

Python
FastAPI
LangGraph or LangChain
OpenAI API or AWS Bedrock
PostgreSQL
pgvector
Docker
Terraform
AWS ECS/Fargate or Lambda

This directly maps to the role’s requirement to build back-end systems, services, orchestration layers and integrations.

2. Add RAG over runbooks and documentation

Create a small knowledge base using your own documents:

AWS incident runbooks
Grafana alert response guides
CloudWatch cost investigation guide
IAM access request guide
Terraform change process
Post-incident review template

Then use RAG so the agent can answer from approved internal-style documentation.

Example:

User asks: “What do I do when CloudWatch costs spike?”
Agent retrieves your CloudWatch cost runbook and gives a structured response.

This would make the project look much closer to an internal government/enterprise AI platform rather than just a normal chatbot.

3. Add proper governance controls

This is probably the most important part for this role.

Add:

user authentication
role-based access control
audit logs
prompt logging
response logging
tool-call logging
approval workflow before actions
sensitive-data redaction
access restrictions by AWS account/environment
immutable logs in S3
CloudTrail/CloudWatch integration

For example:

Feature	Why it helps
Audit logs	Shows traceability
RBAC	Shows access control
Prompt/response logging	Shows AI governance
Approval before action	Shows safe agent design
Redaction	Shows data protection awareness
CloudWatch metrics	Shows operational monitoring

This maps very strongly to the job’s focus on logging, monitoring, auditability, access control, and safe interaction with data/systems.

4. Give the agent safe “tools”

Agentic AI means the AI can use tools/actions, not just answer questions.

Start with safe read-only tools first:

query AWS Cost Explorer data
query Athena cost data
search runbooks
summarise Grafana alerts
inspect CloudWatch metrics
retrieve Terraform module documentation
create an incident summary

Then add controlled write actions:

create a draft Zendesk ticket
create an incident report
suggest an SSM Automation document
generate a Terraform change proposal
create a pull request draft

Do not let it directly change infrastructure at first. Make it “human approval required”.

That shows safe AI deployment, which is exactly what this role cares about.

5. Add monitoring for the AI system itself

Since you already like Grafana, this is where you can stand out.

Build dashboards for:

number of AI requests
failed requests
token usage/cost
average response time
most used tools
blocked unsafe requests
approval/rejection rate
hallucination/low-confidence flags
user feedback score
backend API latency
vector search latency

This would connect your Grafana experience directly to AI governance.

You could call the dashboard:

Agentic AI Governance & Observability Dashboard

That would be very relevant because the role expects technical controls and safe adoption of agent-based AI systems.

6. Add architecture documentation

The role also wants someone who can explain technical concepts, support adoption, document clearly, and work with non-technical teams.

Create documentation such as:

Architecture diagram
Data flow diagram
AI governance model
Security controls
RBAC model
Deployment guide
Runbook examples
Risk register
“How non-technical teams can use this safely”
“What the agent can and cannot do”

------------------------------------------------------------------------

The strongest final project structure

I would build it like this:

Frontend

Simple React dashboard/chat interface
User login
Chat history
Tool activity log
Approval screen

Backend

FastAPI
Agent orchestration with LangGraph/LangChain
RAG pipeline
Tool registry
Approval workflow
Audit logging

Data

PostgreSQL
pgvector
S3 document storage
Athena for AWS cost data
CloudWatch logs/metrics

Infrastructure

Terraform
ECS/Fargate or Lambda
API Gateway/ALB
IAM roles
S3
RDS
CloudWatch
Grafana

Governance

RBAC
audit logs
prompt/response logs
safe tool execution
data redaction
human approval
monitoring dashboards
