# How LLMs Actually Think
*By Kalyani Khona | Last Updated: June 2025*

If we want to understand the structure and hierarchy of LLM's output on different query types, we need to understand the decision making flow of these models. This is a basic 101 document but needed for anyone who is visiting the repo and has no background on LLMs.

### Query processing (gen-query)

1. **Human makes a query**
   - assuming model is pre-trained on it

3. **Query moves to a model that rewrites/reformulates**
   - This query in a format easy to understand by the model
   - Breakdown into set of simpler context (set of keywords that allows it to retrieve information)

4. **Pass to internal search engine**
   - Retrieve pre-trained data + scan web for missing gaps
   - How much data it will retrieve or scan depends on the compute and context length limitation (which is why claude is best here tbh)

5. **Send to summary model**
   - Where each individual source gets a summary

6. **Packaging stage**
   - Where response is generated in natural language with structured text and citations (for human verifications)
  
   ### Deep research (new idea generation, interpretation, inference)

Recently Claude said they do not have just one agent to help with deep research but an army (one agent is gathering citations, second agent is summarising real time as the first agent parses info, third agent is verifying the knowledge and aligning it to claude's constitutional frameworks, another agent is busy packaging). This makes the response time quicker and the quality of response higher. So from this [multi-agent research](https://www.anthropic.com/engineering/built-multi-agent-research-system) system released by them, we already have some understanding of the *deep research* feature which was otherwise a blackbox for a long time. 

Considering the Claude's multi agent blog and my above notes of query processing, I am skipping the in depth breakdown of the deep research flow which is basically gen query + RAG + ranking.

What I do want to talk about is how LLMs brainstorm new ideas. Should you believe everything they recommend for your next GTM strategy? Are they giving this same advice to ten other founders who are in the same domain? These are really important questions to know else I fear we all get misled into doing the same actions thinking they are novel or unqiue to us. 



*This research is part of an ongoing investigation into LLM model behavior patterns. Follow for updates as new patterns emerge and platforms evolve.*
