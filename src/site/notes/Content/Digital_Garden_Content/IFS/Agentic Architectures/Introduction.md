---
{"dg-publish":true,"permalink":"/content/digital-garden-content/ifs/agentic-architectures/introduction/","updated":"2026-07-08T07:47:56.679+05:30","dg-note-properties":{}}
---

## What is the difference between agentic AI and generative AI?

>[!important]
>Generative AI is when we lean towards creativity, we provision a prompt and get back and immediate response with no constraints or reasoning, hence a generative/creative answer. Agentic AI is when we want a prompt to be fed in and then a goal to be achieved. Through a process as such we produce a more exact answer with less diversion. In other words, **generative is reactive** and **agentic is proactive**
>

In a generative flow we would first send a prompt :LiArrowBigRight: then immediately generate a response. However in an agentic flow we would send a prompt :LiArrowBigRight: and then carry out a series of actions. These actions could:

- Perceive the context of what the prompt is asking
- Decide what to do next
- Execute the action that comes next
- Learn from that entire flow to help the LLM understand how it can assume the same flow if a similar question comes up again

Additionally when I say proactively, an agent would first anticipate future events and then take initiative to achieve a goal whereas reactive simply means it will respond to a situation as they occur. 

So, to conclude an agentic architecture follows a proactive approach that ensures a sequence of events to be carried out after a prompt is fed into it to construct a response based on a sequence of deterministic events that produce an outcome that matches a goal.

Furthermore, agentic frameworks consist of steps that come after a prompt is fed in. These steps are actions that follow a flows as such:

![Pasted image 20260615200102.png](/img/user/pngs/Pasted%20image%2020260615200102.png)

## What are agentic architectures and how do they function?

>[!Important]
>An agentic architecture is a proactive workflow we introduce to an LLM so it can follow a certain path to achieve a certain goal. This includes carrying out a sequence of steps after taking in a prompt to execute a sequence of actions that then finally produce an output based on a goal. 

With agentic architectures you will be provisioning an LLM with the following:

- Skills
- Systems Prompts
- Memories
- Tools

Once these attributes have been implemented onto an LLM it leads to the LLM becoming a reasoning engine that is capable of self correction and grounded responses in which it can provide guaranteed responses that is something that we may exactly expect. Take for example asking a question as simple as: "What are my grades?", through an agentic architecture we provision the agent with a knowledge base it can retrieve information from, a step wise approach where it validates itself to ensure a strict answering methodology, a sequence of tool calls to either retrieve information, etc and then finally produce a pure grounded response that provides the engineering team with an audit trail that enables them to deeply debug how and issue may have come up, etc.

A very high level system architecture may look like this:

![Pasted image 20260614163755.png](/img/user/pngs/Pasted%20image%2020260614163755.png)

This a simple approach that uses an architecture achievable through a framework such as Mastra. Refer to the following notes for more contexts