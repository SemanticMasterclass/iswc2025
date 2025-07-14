# OWL or SHACL: A Beginner’s Guide to Making the Right Choice

by Tara Raafat and Davide D'Amico

## Abstract

As knowledge graphs become increasingly integral to enterprise data strategies, the adoption of semantic technologies continues to grow. However, one question arises repeatedly: Should I use Web Ontology Language (OWL), SHApes Constraint Language (SHACL), or a combination of both? This tutorial addresses that question by introducing the core concepts, their practical purposes, and real-world applications of OWL and SHACL, with a focus on understanding when each technology is most appropriate to use. Using a dataset from the museum domain, the session will guide participants through key use cases that demonstrate the distinct strengths and weaknesses of these technologies, as well as where they overlap. Through an example-driven, hands-on approach, attendees will explore how modeling, inference, and data validation are influenced by the use of OWL and SHACL. Participants will collaboratively analyze various problem scenarios to determine the most suitable language(s) for addressing each challenge. The tutorial will involve building ontologies, defining SHACL shapes, and validating data using open source tools. By the end of the session, attendees will have gained practical experience and a clear understanding of how to apply OWL and SHACL effectively in diverse knowledge graph development contexts.

## Overview

This tutorial introduces participants to the core concepts of OWL and SHACL, using museum data to walk through ontology modeling and shape validation. We focus on practical decision-making: which technology is appropriate in a given scenario and why. Participants will engage with structured hands-on tasks and explore the implications of design decisions through guided discussions.
A special emphasis will be placed on helping attendees understand the distinction between working under the Open World Assumption (OWA), which governs OWL, and the Closed World Assumption (CWA), which underpins SHACL. Through an example-based journey using real-world museum data, participants will experience how these assumptions influence data modeling, validation, and reasoning. By comparing how OWL and SHACL behave when information is incomplete or inconsistent, attendees will gain insight into selecting the right tool for their specific data quality and reasoning needs.

## Learning outcomes

- Understand key differences and use cases for OWL and SHACL
- Clarify the implications of the Open World Assumption (OWA) vs. Closed World
- Assumptions (CWA) through hands-on examples
- Gain practical skills creating ontologies and shapes
- Use Protégé and SHACL Playground effectively
- Run SPARQL queries to test models and shapes
- Make informed modeling decisions for real-world problems

## Motivation

Choosing between OWL and SHACL is one of the most fundamental design decisions in the development of semantic applications. Yet, it remains a commonly misunderstood aspect of enterprise data strategies. As the use of knowledge graphs spreads across industries and academia, the need to clearly understand foundational Semantic Web paradigms is becoming more pressing. This tutorial is particularly relevant and timely for ISWC participants, many of whom are either onboarding new team members or working to integrate formal semantics into evolving data infrastructures. By offering a guided, example-based comparison of OWL and SHACL—focusing on their assumptions, logic, and appropriate use cases—we provide a structured framework that attendees can apply in their own projects. Unlike typical tooling or syntax-focused tutorials, this session uses a compelling narrative, example, and interactive hands-on activities to anchor conceptual understanding in real-world relevance.

## Interaction Style

The session blends brief lectures, live tool walkthroughs, and exercises. Sample datasets and pre-built initial models are provided that can be extended or modified by participants. Attendees will be encouraged to create their own OWL models and SHACL shapes as we work through problem scenarios, testing how their modeling decisions impact validation and inference outcomes.
