# How LLMs Actually Think
*By Kalyani Khona | Last Updated: June 2025*
*Ignore typos, I am handtyping this without AI*

If we want to understand the structure and hierarchy of LLM's output on different query types, we need to understand the decision making flow of these models. This is a basic 101 document but needed for anyone who is visiting the repo and has no background on LLMs.

### Query processing (gen-query)

1. **Human makes a query**
   - assuming model is pre-trained on it

3. **Query moves to a model that rewrites/reformulates**
   - this query in a format easy to understand by the model
   - breakdown into set of simpler context (set of keywords that allows it to retrieve information)

4. **Pass to internal search engine**
   - retrieve pre-trained data + scan web for missing gaps
   - how much data it will retrieve or scan depends on the compute and context length limitation (which is why claude is best here tbh)

5. **Send to summary model**
   - where each individual source gets a summary

6. **Packaging stage**
   - where response is generated in natural language with structured text and citations (for human verifications)
  
### Deep research (new idea generation, interpretation, inference)

Recently Claude said they do not have just one agent to help with deep research but an army (one agent is gathering citations, second agent is summarising real time as the first agent parses info, third agent is verifying the knowledge and aligning it to claude's constitutional frameworks, another agent is busy packaging). This makes the response time quicker and the quality of response higher. So from this [multi-agent research](https://www.anthropic.com/engineering/built-multi-agent-research-system) system released by them, we already have some understanding of the *deep research* feature which was otherwise a blackbox for a long time. 

Considering the Claude's multi agent blog and my above notes of query processing, I am skipping the in depth breakdown of the deep research flow which is basically gen query + RAG + ranking.

What I do want to talk about is how LLMs brainstorm new ideas. Should you believe everything they recommend for your next GTM strategy? Are they giving this same advice to ten other founders who are in the same domain? These are really important questions to know else I fear we all get misled into doing the same actions thinking they are novel or unqiue to us. 

Let's take the example of a reseacher wanting to generate novel ideas for his/her next research and asks LLM to give some options.

1. **RAG activated**
   - retrieve all exisitng work done across the internet by crawling google scholar, pubmed and the likes
   - know what is the latest research and discovery in the subject matter of research prompt

3. **Generate a list of ideas**
   - generate 1000s of ideas; way more than a team of humans could do even if they sat for the whole day in a cabin with the whiteboard
     
4. **Pass through pre-defined shortlisting paramters**
   - only a fraction of these ideas get shortlisted for further ranking (need to elaborate later how this shortlisting happens)

5. **Ranking the ideas**
   - model ranks them on interestingness, relevance, etc
   - potentially compare them to papers in the same domain that were already rejected, accepted or highly cited

6. **Proposing a well crafted response**
   - present a set of 5-10 options to the researcher
  
While this may sound exciting, there are limitations with this process. 

1. The ideas are not unique to you or your team. Given the same or similar problem statement could generate the same inputs for your competitor
2. The ideas could be generated on misleading facts or misinformation which affects their feasibility and execution
3. The system lacks intuition and introspection qualities that lead to human ideas being more grounded and thought through
4. Since LLMs have no accountability or execution ownership, some of their ideas may start to feel impossible to execute in a high-stake environment like healthcare, pharma and defence where liability of going wrong is unlimited.

   **I have personally brainstormed with claude and chatgpt with 100s of prompts and upon asking them to criticially evaluate their ideas or asking if they have given the same solution to others, they have confirmed that this is common insight packaged as novel to appeal and keep the user engaged**

   *Knowing all of this, what do I use personally?*

If you use LLMs for serious research and need realiability and maximum breath coverage, use Claude Opus (paid version) because of their multi-agent system framework. They literally appoint an army of agents (sub agents) each given a task, their own context window for parallel reasoning who all report back individually to the lead research agent making the exploration far more advanced in critical thinking and verficiation (this saves you ton of cognitive bandwidth in manually vetting every piece of info).

This is from their own [blog](https://www.anthropic.com/engineering/built-multi-agent-research-system): We found that a multi-agent system with Claude Opus 4 as the lead agent and Claude Sonnet 4 subagents outperformed single-agent Claude Opus 4 by 90.2% on our internal research eval. 

----------
*This research is part of an ongoing investigation into LLM model behavior patterns. Follow for updates as new patterns emerge and platforms evolve.*
