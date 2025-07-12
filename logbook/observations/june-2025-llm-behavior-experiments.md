# 2025 LLM Behavior Research Logbook
Tracking daily experiments, observations, third party conversations and insights on how LLMs behave


---
## WIP

1. NLP principles in LLM design & content optimization 
2. Multimodal search: Images, voice
3. Write taxonomy document [LLM taxonomy document](https://github.com/KK92-ai/llm-model-behavior-research/blob/main/research/llm-search-behavior-patterns-2025.md)
4. Claude citation agent review [citation agent](https://github.com/anthropics/anthropic-cookbook/blob/main/patterns/agents/prompts/citations_agent.md)
5. Work on anatomical framework of LLM responses (experimentation with content type, citation hypothesis and density). [How LLMs think](https://github.com/KK92-ai/llm-model-behavior-research/blob/main/research/how-llms-process-simple-vs-complex-queries-2025.md)
6. ChatGPT shopping recommendation [Improved Shopping Results from ChatGPT Search](https://help.openai.com/en/articles/11128490-improved-shopping-results-from-chatgpt-search)

## July 12, 2025 (Saturday)
- [Research notes](https://github.com/KK92-ai/llm-model-behavior-research/blob/main/research/image_generative_ai_research.md) for the meeting with the founder on image generative AI (computation costs, training data set and GTM)

## July 11, 2025 (Friday)
- NLP principles in LLM design & content optimization [working document](https://github.com/KK92-ai/llm-model-behavior-research/blob/main/research/nlp-principles-model-behavior-geo.md#2-how-models-process--rank-content)

## July 10, 2025 (Thursday)
- [Call with A from Akamai](https://github.com/KK92-ai/llm-model-behavior-research/blob/main/research/generative-search-ai-strategy-notes.md) to discuss investment updates, feedback on ongoing research, new trends in LLMs etc.
- Key takeaway: The GEO space is ripe for disruption but there's a narrow window (6-12 months) before big tech platforms integrate these capabilities natively. Focus on actionable insights (and agentic execution) rather than just monitoring might provide more sustainable value.

## July 9, 2025 (Wednesday)

- [Research notes](https://github.com/KK92-ai/llm-model-behavior-research/blob/main/research/prompt-engineering-vs-fine-tuning-when-to-use-2025.md) on prompt engineering vs fine tuning, cost benefit analysis, model priority matrix
- Research notes and insights on GEO/AEO, LLM behaviour with [neusearch team](https://neusearch.ai/) - [findings here](https://github.com/KK92-ai/llm-model-behavior-research/blob/main/research/ai-search-optimization-market-insights-july-2025.md)
- ChatGPT x Bing for internet search

## July 8, 2025 (Tuesday)

- Understanding the basics of Llama base model and assistant model, parameters, pre-training data, fine tuning etc
- ***Base model (pretraining)***: download text from the internet -> get GPU clusters -> compress the text into neural net -> pay $$ mn, wait for 10-12 days -> obtain base model
- ***Assistance model (finetuning)***: once you have the base model -> write labeling instructions i.e how your AI should behave -> scale AI to collect 100K high quality formatted responses -> feed into base model data and wait for 1 day -> obtain assitant model -> run evals -> deploy -> monitor behaviour -> iterate i.e. go back to labeling instructions
- ***Finetuning via comparision labels*** or RLHF (optional) in situations where humans may not be able to write answers or have limited context. OpenAI did this with its actual users/early adopters since the early days.

## June 27, 2025 (Friday)
- Understanding the decision making workflow of a search query [How LLMs think](https://github.com/KK92-ai/llm-model-behavior-research/blob/main/research/how-llms-process-simple-vs-complex-queries-2025.md)

## June 26, 2025 (Thursday)
- Finalised the anatomical framework I will be using to compare results across LLMs.
- Started working on the [LLM taxonomy document](https://github.com/KK92-ai/llm-model-behavior-research/blob/main/research/llm-search-behavior-patterns-2025.md) for cross referencing.
- Started testing perplexity on "tell me everything about Kalyani Khona" through multiple formats - general query and deep research feature.

## Early observations on Perplexity
- Surprised that given the same exact query, Substack was quoted and crawled for deep research report while the LLM skipped it during the general response (probably because the memory is not trained on it?).
- General response gave out a summary table which was based on the interpretation of all the sources it crawled. Pretty accurate to be honest.
- Deep research feature also crawled my social media (instagram) and college alumni group.
- Freshness is not that fresh considering how perplexity cites the latest information. More in the detail report.
- Shocked that perplexity completely skipped wikipedia in both deep research and general query output.
- Fact: SEO still matters, public relations is not dead. People should maintain their own webpage and a blog/newsletter. All of this will become very useful in the coming times.
- History is still important, especially in general queries where the LLMs are trained on ancient data.
- The best part of this experiment was to learn that it has developed its own personal (philosophical) narrative on "Kalyani Khona" based on everything it learnt by using pattern recognition.

### Next steps

- Analyse and review Perplexity's responses in detail across various parameters (move notes from the logbook)
- Once the whole process is finalised and reported structurally, repeat the same across other LLMs to compare results. 

---
## Research Status
*This is a living document updated daily as part of my LLM behavior research.*

**Model Leaderboard**
[tracker](https://lmarena.ai/leaderboard)

**Research Focus**: Understanding LLM response patterns, generative engine optimization, answer engine optimization, NLP deep dive on content density, citation behaviors and landscape, and platform-specific content type/format preferences

**Last Updated**: July 9, 2025 | 5:20 PM IST

**Contact**: [LinkedIn](https://linkedin.com/in/kalyanikhona) | [GitHub](https://github.com/KK92-ai)
