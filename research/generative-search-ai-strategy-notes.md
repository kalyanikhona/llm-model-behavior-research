# Generative Engine Optimisation (GEO) Strategy Discussion - Technical Insights & Market Analysis

**Document Type:** Planning Notes  
**Date:** July 9, 2025  
**Focus:** GEO, Multi-Agent Systems, Competitive Timeline Analysis  
**Source:** Discussion with *title retracted*

---

## Executive Summary

This document captures strategic insights from technical discussions focusing on Generative Engine Optimization (GEO), multi-agent marketing systems, and competitive timeline analysis for attribution tools. 
Key findings include a 6-12 month window before basic attribution becomes commoditized, significant transparency gaps in current big tech offerings, and opportunities in the Indian market for specialized AI solutions.

---

## LLM Challenges and Limitations

### Hallucination and Misinformation
- Hallucination has improved but remains a significant issue
- Heavy reliance on "fact-checking" systems that can become stale over time (RAG needs frequent updates)
- Model fine-tuning can introduce biases or manipulative suggestions (unintentional)
- Identifying fabricated facts without external tools remains difficult for users

### Memory and Computational Constraints
- **Long-term memory issues**: Computational costs and "catastrophic forgetting" limit LLM memory capabilities (liquid AI has a breakthrough but they have not been ready for public use and may not be able to compete the existing large models on real world applications)
- **Scale problems**: While increased compute power could improve memory, there are inherent limitations due to the nature of neural networks and the scale of user data
- **Current solutions to memory**: ChatGPT uses caching/retrieval for conversations, enterprise systems using RAG with controlled datasets
- **Evolution**: Training methods largely unchanged, but scaling laws and data preprocessing improvements drive performance gains

### Interpretability Challenges
- LLMs perform pattern matching and prediction, not genuine reasoning
- Model size creates interpretability challenges for independent researchers/labs (frontier lab models are opaque)
- Still required even for tasks like sentiment analysis through fine-tuning
- Surprising ability to handle new tasks that the model has not been trained on before, but underlying mechanisms remain opaque

---

## GEO (Generative Engine Optimization) and Brand Visibility 

### Current Market Challenges
- Traditional SEO attribution methods don't apply to AI-generated content
- Heavy reliance on traditional SEO, limited GEO adaptation
- Difficulty in computing probabilities of brand visibility in AI outputs
- Equating chat probability with actual brand visibility may be misleading (chatgpt vs AI overview)

### Advanced Attribution Metrics 
**Recommended Measurement Framework:**
- **Response positioning**: Where brand appears in LLM response (first mention, primary recommendation, etc.)
- **Context relevance**: Semantic relevance of brand mention to user query intent
- **Citation quality**: Source attribution vs. casual mention vs. direct recommendation
- **Sentiment context**: Positive, neutral, or negative framing of brand mention
- **Competitive displacement**: Whether brand mention replaces competitor visibility
- **Query type alignment**: Performance across transactional vs. informational vs. navigational queries
- **Follow-ups**: Likelihood to generate clarifying questions or deeper exploration
- **Response completeness**: How well brand mention satisfies user's information need
- **Multi modal**: Brand visibility across text, image, and voice responses

### Strategic Opportunities
- **LLM content monitoring**: Track how LLMs interact with web content (suggestion to monitor LLM interactions with web content and developing strategies to make content more accessible to these models)
- **Content accessibility**: Develop strategies to make content more LLM-accessible (format, style and sources)
- **Create and distribute layer**: Focus on content creation/distribution rather than just tracking/analysis (idea: own multiple indepedent blog websites which can auction spots for brands)
- **Commoditization risk**: Major players (Google, OpenAI) may build internal attribution tools

### Competitive Timeline Risk Assessment 

**Refined Timeline Based on Market Research:**

**Basic Brand Mention Tracking: 3-6 months**
- **Google**: Technical infrastructure exists, likely integrated into Search Console within 3-6 months
- **OpenAI**: Enterprise demand driving development, 3-6 months for basic ChatGPT Enterprise analytics

**Sophisticated Attribution with Conversion Tracking: 6-18 months**
- **Google**: 6-12 months for paid search attribution (strong revenue incentive), 12-18 months for organic attribution (ecosystem pressure but transparency conflicts)
- **OpenAI**: 9-15 months as enterprise suite expands with business tool integrations

**Full Attribution Suites: 12-24 months**
- **Google**: 18-24 months, strategically limited to show favorable metrics to publishers (assumption that an independent platform will still be in demand)
- **OpenAI**: 12-18 months, likely more transparent (assumption: no publisher ad revenue dependency)

**Google's Conflicted Incentives:**
- **Pro-attribution drivers**: Publisher ecosystem preservation, regulatory pressure, competitive defense against revenue-sharing models
- **Anti-transparency drivers**: Risk of revealing negative publisher impacts, potential demands for revenue sharing
- **Strategic limitation**: Tools will likely emphasize positive metrics while obscuring negative impacts (biased output)

---

## Multi-Agentic Systems Platform

### Multi-Agent Marketing Workflow Architecture
**Proposed Agent Specializations:**
- **SEO specialist agent**: Technical optimization, keyword research, on-page optimization
- **Content creation agent**: Blog posts, product descriptions, meta content generation
- **Performance monitoring agent**: Ranking tracking, traffic analysis, conversion attribution
- **Distribution agent**: Content syndication, social media posting, email campaigns
- **Competitive intelligence agent**: Competitor content analysis, gap identification
- **Quality assurance agent**: Content review, brand voice consistency, fact-checking

**Workflow Integration Points:**
- Content creation → SEO optimization → distribution → monitoring → iteration
- Real-time feedback loops between monitoring and content creation agents
- Cross-agent learning from performance data

**Core Strategy Beyond Attribution:**
- Diversification if GEO attribution market becomes commoditized by big tech
- Leverages same core LLM expertise but different market application
- Addresses broader marketing automation needs beyond just attribution

### Technical Architecture Trends
- **Large world models**: Industry shift towards processing multiple data modalities (text, image, voice, video)
- **[Liquid AI]([https://www.liquid.ai/](https://github.com/Decentralised-AI/LFM-Liquid-AI-Liquid-Foundation-Models)) Alternative (non GPT) LLM architecture methodologies. They've essentially solved the "scaling problem" that has made long-context processing so expensive and slow.
- **Enterprise vs consumer scale**: Different approaches needed for controlled enterprise datasets vs. massive consumer-scale challenges
---

## AI Content Detection and New Training Data

### AI Labs's Data Preference (Hypothesis)
**Current Industry Trend:** AI labs actively seek authentic human-generated content for training data and increasingly filter out AI-generated content.

**Technical Rationale:**
- Training AI on AI-generated content can lead to degraded performance over time
- Human-created content provides diverse perspectives and genuine insights
- Improving AI content detection tools (watermarking, statistical analysis, linguistic patterns)
- Human content generally has better fact-checking and editorial oversight

**Implications for Content Strategy:**
- Premium value for verifiably human-created content
- AI-assisted but human-reviewed content may maintain value
- Content generation tools vs. detection tools in continuous evolution
- Potential market premium for high quality well-written content by humans

**Content Strategy Recommendations:**
- Emphasize human expertise and unique insights in content creation
- Implement clear authorship attribution and editorial processes
- Focus on structuring and formatting high quality data (debate is whether it matters if it is in LLM friendly format as they are trained to crawl the web irrespective and then process/clean up the data)

---

## Research and Development Priorities

### Immediate Focus Areas 
1. Citation landscapes and format optimization for brand visibility
2. Effectiveness analysis for multi-metric tracking systems  
3. Specialized agent development for marketing automation
5. Advanced metrics beyond simple chat probability (stay ahead and solve for multi-modal)
---

## Insights

**The Transparency Gap Opportunity**
Current evidence shows Google doesn't separate AI Overviews click-throughs from regular search referral traffic in Analytics/Search Console, leaving publishers "in the dark." 
This creates a significant opportunity for independent tools that provide the complete, unbiased picture that Google is incentivized to obscure.

**Critical Success Factor: Speed to Market**
With basic attribution tools 3-6 months away, the company needs to prioritize core features and establish market presence before commoditization occurs. 
Focus on the advanced metrics framework (response positioning, sentiment context, competitive displacement) as differentiation from basic mention tracking.

OpenAI is focused on general enterprise productivity and analytics tools. There's no evidence they're building brand visibility tools, which creates a clearer opportunity for us. 

---

**Document Status:** Final Analysis  
**Next Steps:** MVP development prioritization  
**Last Updated:** July 2025
