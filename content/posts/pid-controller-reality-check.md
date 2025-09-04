---
title: "The PID Controller Reality Check for AGI"
date: 2025-09-01T00:00:00Z
draft: false
description: 
tags: ["Reflections", "AI", "Engineering", "Control Systems"]
categories: ["Reflections"]
---


In this post, I would like to think about agents that already run our world. They are not the fancy agents that have come to dominate the technology discourse. They are time-tested workhorses. To understand the true challenge of creating a trustworthy autonomous system, I propose to think about the most successful and widely deployed agent in history: the Proportional-Integral-Derivative (PID) controller.  

I choose the PID controller precisely because it is simple, real, and tested time again in the real world. It is a decision-making policy in its purest form. While the control algorithm itself is well-studied, the enormous amount of engineering required to make it operate reliably highlights the critical gap between an abstract algorithm and a functioning agent. Analyzing these necessary steps provides a crucial reality check for any credible claim about autonomy.  

While we do not commonly think of “controllers,” such as PIDs, as agents, they do fit the definition of an agent squarely. As the authors of *Artificial Intelligence: A Modern Approach* write:  

> An agent is anything that can be viewed as perceiving its environment through sensors and acting upon that environment through actuators.  

Under this definition, and under any reasonable conception of what an agent is, I think it is difficult to argue otherwise.  

### The PID Controller as an Embedded Concept  

Much of today’s AI discourse assumes that the hard problem of autonomy is solved once we can specify a policy that makes the “right” decisions. The PID loop shows otherwise. Here is a policy so transparent it can be written on a single line, and still, its usefulness depends almost entirely on the engineering that surrounds it. The insight is not about how to decide, but about how that decision logic behaves once it is coupled to sensors, actuators, and other agents in the world.  

A PID loop calculates an action from three ingredients: error in the present, error accumulated from the past, and a prediction of error to come. That is the entirety of its “intelligence.” But once this rule is placed in a real environment, the picture changes. The formula must be tied to sensors that drift, actuators with limits, and processes that behave differently than their models.  

Consider the seemingly ordinary task of controlling the level in a water tank. On paper, the rule is trivial: if the level is too low, open the valve; if it is too high, close it. In practice, the controller must account for noisy measurements, delays in valve response, nonlinear flow, and interaction with other loops in the plant.  

This is why the PID is such a useful case study. It shows how a compact idea acquires complexity when embedded in the world. On paper it is almost trivial; in practice, making it reliable requires careful attention to measurement, actuation, and coordination.  

So, my question is, if such a straightforward recipe for action becomes difficult in practice, what should we expect from agents whose workings we do not even fully understand?

### Where the Work Really Lies  

The PID equation says little about what it takes to make a controller trustworthy. That work happens in the surrounding design:  

- **Mapping to the physical world.** “Error” must be defined through sensors that are noisy, biased, or drifting. “Action” must be expressed through actuators that have hard limits, delays, and wear.  
- **Tuning to dynamics.** Gains that work in one process can destabilize another. Responsiveness and stability must be balanced against the specific physics of the system.  
- **Handling limits.** Without safeguards, a controller will command impossible actions. Anti-windup measures prevent internal states from drifting away from what is physically achievable.  
- **Managing modes and handovers.** Operators must be able to intervene, and control must pass back smoothly. This requires protocols like bumpless transfer, which keep internal states aligned with the plant.  
- **Interacting with peers.** Controllers rarely operate in isolation; their actions create disturbances for others. Stability emerges at the system level, not from any single loop.  

None of this complexity is visible in the compact formula, yet it is what turns the concept into a functioning agent.  

### Lessons for Autonomy  

These days, agents almost always come up in the context of "LLM agents". But these agents do not act in the physical world. They output text or trigger software calls. In the physoical world, without instruments, actuators, and the architecture that binds decisions to consequences, these outputs remain proposals, not actions. When such outputs are coupled to physical systems, the problem changes class: measurements carry error and drift, actuators have limits and delays, interactions create feedback and risk. For this reason, an LLM agent is not a satisfactory recipe for autonomy. Autonomy is a property of an embedded system, not of a standalone policy.

The hard part of autonomy is not inventing new rules of action, but designing the structures that let those rules operate safely and predictably in the world. Replace the water tank with a vehicle, or the valve with a supply chain decision, and the same truth holds: the abstract policy is never enough.  

### So?  

A PID loop is a small honest agent we trust with physical processes. It earns that trust not because its logic is sophisticated but because engineers have built the structures that make it reliable: calibration of inputs, constraints on outputs, safeguards against instability, and mechanisms for human interaction.  

If even this elementary agent demands such care, then bold claims of imminent “autonomous” intelligence deserve rigorous scrutiny.



