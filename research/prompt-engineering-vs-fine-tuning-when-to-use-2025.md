# Prompt engineering vs fine tuning base models (when to use what methodologies)

### Decision making framework (parameters):

- **Cost comparison**: Prompt engineering vs fine-tuning
- **Control level**: What each approach can/can't achieve
- **Scalability**: Which approach works for different company sizes
- **Risk assessment**: Potential downsides of each strategy

Question - How can brands ethically influence their representation in AI outputs?

- **Baseline testing**: How do models currently mention specific brands?
- **Fine-tuning experiments**: Can training data shift brand sentiment?
- **Prompt optimization**: Alternative approaches to brand positioning
- **Ethical boundaries**: What's legitimate vs manipulative?

## Model Priority Matrix

- **High Impact**: ChatGPT, Gemini (direct user interaction)
- **Medium Impact**: Perplexity, search integration models
- **Emerging**: Industry-specific fine-tuned models

## Strategy 

### Level 1: Content Strategy (TG: Startups, D2C brands, SMEs)
- Optimize existing content for AI training data
- Create AI-friendly FAQ formats
- Structured data markup for AI consumption

### Level 2: Fine-Tuning Investment (TG: Mid-tier firms wanting RAG + internal LLM capabilities built on base models)
- Cost: $5K-50K depending on scope
- Timeline: 2-4 months including testing
- Risk: Model dependency, ethical concerns

**Shortcomings**: Fine-tuning only works for internal/owned systems (best leveraged by companies like Mckinsey and likes)

- A brand's fine-tuned model sits on their servers
- When users ask ChatGPT "best smartphone?", they're hitting OpenAI's models, not the brand's
- Fine-tuning creates isolated islands of influence, not broad market impact

Most AI consultants sell fine-tuning without acknowledging this fundamental distribution problem.

### Level 3: Model Partnerships (TG: Only large enterprises like Microsoft and Apple can afford this)

- Direct partnerships with AI providers
- Custom fine-tuning agreements
- Brand safety controls

**Shortcomings**: Only mega-enterprises have leverage for model partnerships

- Compromises perceived neutrality and trust by end users (if they know the models have been manipulated to recommend a certain brand over another - making it advertorial) 
- Regulators oppose dynamics like this actively
- Providers can't do custom deals with every brand (scalability problems)

Fine-tuning on open source base models only affects systems you own, not where customers actually are. This is why all brand's AI visibility strategy should focus on discovery and content optimisation for closed source, chat interface models like Chatgpt and Gemini by feeding them high quality relevant training data.

## Thoughts on the long term benefits of finetuning internal AI models for consulting companies:
  - Companies that need AI strategy must think of context or finetuning seriously. How you give AI the data and information it needs to make decisions, communicate to your internal teams as well as external clients sets the tone and vision for the brand.
  - "Context" is actually how the company operates; the ideal versions of your reports (formats), documents (language and type) & processes that the AI can use as a model; the tone & voice of your organization.
  - Don't offload how your company operates to some sort of RAG search of every document in your shared storage. Make choices about what kinds of context you need, build the ideal version of a report or document or instruction manual, and take context seriously.

## Summary:

- The distribution problem is real and under-discussed
- Fine-tuning is relevant for internal ops (HR, legal) but marketing and brand teams need to work with existing closed-knit LLMs by providing high quality training data
- "Where are customers actually interacting with AI" is an important question to ask (if its travel or finance, you will find your users on perplexity or chatgpt, if its SaaS or coding, you'll find your end user on claude and so on)
