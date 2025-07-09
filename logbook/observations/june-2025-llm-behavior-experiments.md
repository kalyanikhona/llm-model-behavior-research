# 2025 LLM Behavior Research Logbook
Tracking daily experiments, observations, third party conversations and insights on how LLMs behave (Note: For now I am dumping all my notes here but eventually I will move them to relevant files and folders)

---
## July 9, 2025 (Wednesday)

## Prompt engineering vs fine tuning base models (when to use what methodologies)

### Decision making framework (parameters):

- **Cost comparison**: Prompt engineering vs fine-tuning
- **Control level**: What each approach can/can't achieve
- **Scalability**: Which approach works for different company sizes
- **Risk assessment**: Potential downsides of each strategy

Question: How can brands ethically influence their representation in AI outputs?

- **Baseline testing**: How do models currently mention specific brands?
- **Fine-tuning experiments**: Can training data shift brand sentiment?
- **Prompt optimization**: Alternative approaches to brand positioning
- **Ethical boundaries**: What's legitimate vs manipulative?

## Model Priority Matrix
- **High Impact**: ChatGPT, Gemini (direct user interaction)
- **Medium Impact**: Perplexity, search integration models
- **Emerging**: Industry-specific fine-tuned models

## Strategy Options
### Level 1: Content Strategy (TG: Startups, D2C brands, SMEs)
- Optimize existing content for AI training data
- Create AI-friendly FAQ formats
- Structured data markup for AI consumption

### Level 2: Fine-Tuning Investment (TG: Mid-tier firms wanting RAG + internal LLM capabilities built on base models)
- Cost: $5K-50K depending on scope
- Timeline: 2-4 months including testing
- Risk: Model dependency, ethical concerns

### **Shortcomings**: Fine-tuning only works for internal/owned systems (best leveraged by companies like Mckinsey and likes)

- A brand's fine-tuned model sits on their servers
- When users ask ChatGPT "best smartphone?", they're hitting OpenAI's models, not the brand's
- Fine-tuning creates isolated islands of influence, not broad market impact

Most AI consultants sell fine-tuning without acknowledging this fundamental distribution problem.

### Level 3: Model Partnerships (TG: Only large enterprises like Microsoft and Apple can afford this)

- Direct partnerships with AI providers
- Custom fine-tuning agreements
- Brand safety controls

### **Shortcomings**: Only mega-enterprises have leverage for model partnerships

- Compromises perceived neutrality and trust by end users (if they know the models have been manipulated to recommend a certain brand over another - making it advertorial) 
- Regulators oppose dynamics like this actively
- Providers can't do custom deals with every brand (scalability problems)

Fine-tuning on open source base models only affects systems you own, not where customers actually are. This is why all brand's AI visibility strategy should focus on discovery and content optimisation for closed source, chat interface models like Chatgpt and Gemini by feeding them high quality relevant training data.

## Summary:

- The distribution problem is real and under-discussed
- Fine-tuning is relevant for internal ops (HR, legal) but marketing and brand teams need to work with existing closed-knit LLMs by providing high quality training data
- "Where are customers actually interacting with AI" is an important question to ask (if its travel or finance, you will find your users on perplexity or chatgpt, if its SaaS or coding, you'll find your end user on claude and so on)

### Research notes and insights on GEO/AEO, LLM behaviour with [neusearch team](https://neusearch.ai/). [findings here](https://github.com/KK92-ai/llm-model-behavior-research/blob/main/research/ai-search-optimization-market-insights-july-2025.md) 

## July 8, 2025 (Tuesday)

- Understanding the basics of Llama base model and assistant model, parameters, pre-training data, fine tuning etc
- ***Base model (pretraining)***: download text from the internet -> get GPU clusters -> compress the text into neural net -> pay $$ mn, wait for 10-12 days -> obtain base model
- ***Assistance model (finetuning)***: once you have the base model -> write labeling instructions i.e how your AI should behave -> scale AI to collect 100K high quality formatted responses -> feed into base model data and wait for 1 day -> obtain assitant model -> run evals -> deploy -> monitor behaviour -> iterate i.e. go back to labeling instructions
- ***Finetuning via comparision labels*** or RLHF (optional) in situations where humans may not be able to write answers or have limited context. OpenAI did this with its actual users/early adopters since the early days.
- Add to task: review Anthropic [citation agent](https://github.com/anthropics/anthropic-cookbook/blob/main/patterns/agents/prompts/citations_agent.md)

## Thoughts on the long term benefits of finetuning internal AI models for consulting companies:
  - Companies that need AI strategy must think of context or finetuning seriously. How you give AI the data and information it needs to make decisions, communicate to your internal teams as well as external clients sets the tone and vision for the brand.
  - "Context" is actually how the company operates; the ideal versions of your reports (formats), documents (language and type) & processes that the AI can use as a model; the tone & voice of your organization.
  - Don't offload how your company operates to some sort of RAG search of every document in your shared storage. Make choices about what kinds of context you need, build the ideal version of a report or document or instruction manual, and take context seriously.

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

The best part of this experiment was to learn that it has developed its own personal (philosophical) narrative on "Kalyani Khona" based on everything it learnt by using pattern recognition. Recording it here for the future reference.

**Personal philosophy: Khona’s work is anchored in the belief that “no one deserves to be alone unless they wish so” and that technology should respect human psychology before code. Her career illustrates a consistent pattern: find an ignored user segment, study its behavioural constraints, then build accessible, behaviour-led products**.


Side note: I am worried that these experiments are going to ruin my personal profile (by confusing the LLMs) considering I am playing with random keywords on my web page and other platforms that I can control but probably figure all that later. 

### Next steps
- Complete writing the taxonomy document (living document as models keep updating themselves).
- Publish the anatomical framework on Github
- Analyse and review Perplexity's responses in detail across various parameters (move notes from the logbook)
- Once the whole process is finalised and reported structurally, repeat the same across other LLMs to compare results. 


---
## Research Status
*This is a living document updated daily as part of my LLM behavior research.*

**Research Focus**: Understanding LLM response patterns, citation behaviors, and platform-specific content type/format preferences

**Last Updated**: July 8, 2025 | 9:45 PM IST

**Contact**: [LinkedIn](https://linkedin.com/in/kalyanikhona) | [GitHub](https://github.com/KK92-ai)
