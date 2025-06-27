# How LLMs Actually Think
*By Kalyani Khona | Last Updated: June 2025*

If we want to understand the structure and hierarchy of LLM's output on different query types, we need to understand the decision making flow of these models. This is a basic 101 document but needed for anyone who is visiting the repo and has no background on LLMs.

### Query processing flow (gen-query

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



*This research is part of an ongoing investigation into LLM model behavior patterns. Follow for updates as new patterns emerge and platforms evolve.*
