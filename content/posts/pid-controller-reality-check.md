---
title: "The PID Controller Reality Check for AGI"
date: 2025-09-01T00:00:00Z
draft: false
description: 
tags: ["Reflections", "AI", "Engineering", "Control Systems"]
categories: ["Reflections"]
---



In the post, I would like to think about agents that already run our world. They are not the fancy agents that have come to dominate the technology discourse. They are time-tested workhorses. To understand the true challenge of creating a trustworthy autonomous system, I propose to think about the most successful and widely deployed agent in history: the Proportional-Integral-Derivative (PID) controller.  

I choose the PID controller precisely because it is simple, real, and tested time again in the real world. It is a decision-making policy in its purest form. While the control algorithm itself is well-studied, the enormous amount of engineering required to make it operate reliably highlights the critical gap between an abstract algorithm and a functioning agent. Analyzing these necessary steps provides a crucial reality check for any credible claim about autonomy.  

While we do not commonly think of “controllers,” such as PIDs, as agents, they do fit the definition of an agent squarely. As the authors of *Artificial Intelligence: A Modern Approach* write:  

> An agent is anything that can be viewed as perceiving its environment through sensors and acting upon that environment through actuators.  

Under this definition, and under any reasonable conception of what an agent is, I think it is difficult to argue otherwise.  


## The PID Controller as the Smallest Honest Agent  

A PID loop is deceptively simple: it calculates an action from three ingredients—error in the present, error accumulated from the past, and a prediction of error to come. That is the entirety of its “intelligence.” Yet the moment we try to use this agent in the physical world, the simplicity evaporates. What emerges is not an abstract formula but an engineered system, one that must wrestle with ambiguity, noise, limits, and safety.  

This is why the PID is such a useful case study. It shows, in miniature, the distinction between *algorithm* and *agent*. The formula may fit on a single line, but turning it into a trustworthy operator demands a whole architecture around it.  

So, my question is, if such a simple and transparent recipe of action becomes more challenging in practice, what can that tell us about agents that we don’t understand?  

It should give us pause. A PID controller is not mysterious. Every term can be written on a napkin, every parameter has a physical interpretation, and yet its reliable use demands a careful architecture of safeguards, conventions, and coordination. If this is what it takes for the most elementary agent we know, then the promise of deploying far more complex and opaque agents—ones whose inner workings we cannot summarize on a single line—cannot be taken at face value.  

The lesson is not that autonomy is impossible, but that autonomy is never just the policy. An agent’s intelligence is inseparable from the scaffolding that makes it robust: the way its inputs are measured, the way its outputs are constrained, the way it interacts with other agents and with human operators. With PID controllers, engineers learned this lesson through decades of trial, error, and sometimes costly failures.  

The challenge before us now is to recognize that advanced agents will need their own versions of this scaffolding—principles of tuning, limits, handover, and coordination adapted to their domains. Without this surrounding structure, they remain what the bare PID equation would be on its own: a clever idea, not a trustworthy operator.  


## Lessons for Autonomy  

The analogy to today’s discourse on autonomy is direct. Replace the water tank with a vehicle, or the valve with a supply chain decision, and the same truth holds: the algorithm is never the agent. The reality of sensors, actuators, dynamics, limits, coordination, and human operability cannot be waved away.  

When AI researchers present a new policy or model as an “agent,” the PID loop offers a sobering reminder. Unless the messy work of grounding, tuning, limiting, and coordinating is addressed, we are looking at an equation, not an operator. A credible agent is not defined by clever decision logic alone but by the full system of engineering that makes those decisions safe, stable, and usable.  


## Conclusion  

A PID loop is the smallest honest agent we trust with physical processes. It earns that trust not because its logic is sophisticated but because decades of engineering have wrapped it in mechanisms that account for measurement, actuation, timing, limits, safety, and handover. If even this tiny agent requires such care, then any claim of “autonomous” intelligence must be judged against the same standard.  

An agent that cannot yet control a tank of water has no business declaring itself fit to govern the world.  


