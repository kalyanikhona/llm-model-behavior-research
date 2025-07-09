# AI Search Optimization Insights with [Neuverge Labs Private Limited](https://neusearch.ai/)
*Research Notes by Kalyani Khona | July 8, 2025*

## Key Takeaways

- Recognition that GEO is fundamentally different from SEO
- Understanding that temperature/randomness affects consistency
- Focus on D2C/e-commerce as a good initial market (product comparisons are indeed common LLM queries)
- Platform approach with integrations is the best way forward (to avoid building redundancy)
- Multi-agent architecture could work well for content analysis

## Challenges with content optimization

- **Reverse engineering visibility**: LLMs don't have a ranking algorithm (pagerank) like Google. Their responses depend on complex interactions between pretraining data, fine-tuning, and prompting quality
- **Forcing web search visibility**: You cannot force a web search on user's part. Remember that many generic or basic LLM interactions don't involve web search at all. They rely on pre-trained knowledge
- **Content "pickup" by LLMs**: For pre-trained models, the content needs to exist before training cut-offs and be in crawlable, high-quality sources. For RAG systems, we are competing with real-time search results

## Market Awareness Gap
- Most marketers view AI search as "SEO 2.0" rather than a distinct field, market still nascent (5-10% inbound traffic right now is from ChatGPT)
- Two types of clients: Experimental clients (just explore and learn with minimal investment) vs informed clients (coming with a specific ask -> demo -> move to execution)
- Limited awareness about execution capabilities and differences between traditional SEO and AEO
- Content training data knowledge missing, same with execution know-how
- Marketers understand basic AI models (ChatGPT) but not from the optimization implications. They simply use it for content creation (generation)
- Existing marketers positioning AI search as SEO extension missing the paradigm shift and what it takes to generate content optimised for AI training data

### Market Segmentation Insights

**High Interest Segments:**

- D2C companies (faster market fit, can productize the playbook, recurring sales potential). Currently use influencer marketing and quick commerce ascore distribution channel but if shown promising results, we could create a playbook and productise the offering
- B2B SaaS companies (understand tech differentiation using comparision format training data)
- E-commerce platforms (need product visibility in AI responses)

**Low Interest Segments:**

- Large enterprises with established market share
- Service-based companies (longer sales funnels)
- Traditional SEO-focused agencies

## Technical Insights

### LLM Behavior Patterns Observed

- ChatGPT provides inconsistent results for identical queries (run lesser prompts but with higher frequency to improve accuracy)
- Heavy reliance on Reddit and user-generated content for product recommendations (all search results for earbuds and furniture rental had a section called "what users say" which was picked from Reddit
- Temperature settings significantly impact response consistency
- Web search vs non-web search queries show distinct behavior patterns (most AI tracking tools show citations across all queries, including non-web search)

### Content Strategy Findings

- AI-generated content performs well on LinkedIn, poorly on Twitter/Instagram
- Product comparison documents specifically formatted for LLMs show promise
- Citation patterns vary significantly across platforms (need to map the citation landscape across different LLMs)

## Product Development Insights

### Critical Success Factors

1. **Accuracy over features**: Trust metrics more important than feature count
2. **Transparency**: Show probability indicators for visibility confidence (with weekly update on improvement in the probabilities as we get thorough with research)
3. **Platform approach**: Integration with existing SEO tools creates competitive advantage (multi agent system running GEO ops and optimisation)

## Action Items

- **Citation analysis tool**: Build a tool that tracks when and how brands are mentioned across different LLM platforms
- **Content optimizer**: Develop specific templates optimized for LLM comprehension (structured data, clear hierarchies, factual density)
- **Query intent mapping**: Create a system to identify high-value queries in our clients' industries and optimize for those specific patterns

### Pricing Model Learnings

- Feature-based pricing resonates better than prompt-based
- Free tier should be demo-only
- Per-competitor tracking model (similar to Meltwater) shows promise
- Three-tier structure optimal for market entry

## Competitive Landscape Observations

### Current Market Dynamics
- New entrants focusing on "AI SEO" missing the bigger picture
- Agencies averaging 6-month turnaround for optimization projects
- Multi-agent systems showing promise for workflow automation

### Differentiation Opportunities

- Content analysis predicting likelihood of LLM citing the content piece
- Reverse-engineering visibility patterns
- Automated workflow reducing turnaround from 6 months to 3 months
- Citation landscape tracking as premium feature (mindmaps and word clouds)

## Strategic Recommendations

### Go-to-Market Approach

1. Focus/shortlist on e-commerce/D2C as GTM
2. Develop vertical-specific playbooks (coffee, earbuds, furniture rental examples)
3. Lead with research-backed content, not sales metrics (research > sales)
4. Position as novel multi-agent platform, not just another GEO tool or SEO replacement option

### Technical Priorities

- Multi-agent architecture for content optimization
- Temperature control and result averaging for consistency
- Focus on accuracy and probabilities 
- Dashboard showing citation trends over time
- Integration layer for third-party SEO tools

## Action Items

- **Testing framework**: Create a system to systematically test how different content formats perform across multiple LLMs and query types
- **Focus on RAG optimization**: Since we can't influence pre-training, focus on optimizing for retrieval systems (Perplexity, ChatGPT with browsing, etc.)
- **Tracking infrastructure**: Build robust attribution tracking that can handle the probabilistic nature of LLM responses. Think of multi layer tracking architecture (query monitoring), setup automated query testing bots, parse responses (brand mention, competitors, citation url when mentioned, sentiment analysis). Give confidence scores to results. 

## Dashboard Components:

  - Format Performance Matrix: Shows which formats work best for which query types
  - Compare performance across different LLMs
  - Trend Analysis: Track performance changes over time
  - A/B Test Results: Statistical significance of content changes
  - Estimate value of improved visibility

## Performance Indicators:

metrics = {
    "mention_rate": "Percentage of times brand/product is mentioned",
    "position_score": "Average position in response (1st mention = 1.0)",
    "citation_rate": "How often URL is cited (if applicable)",
    "accuracy_score": "Factual accuracy of information presented",
    "prominence_score": "Word count dedicated to your brand vs others",
    "sentiment_score": "Positive/negative context of mentions",
    "feature_recall": "Which features are mentioned from your content"
}

## Content Density Indicators:

1. **High density content (information rich)**

LLMs prefer this when:
- Technical queries
- Expert-level questions
- Detailed comparisons

2. **Medium density content (balanced view)**

LLMs prefer this when:
- General information queries
- Standard product searches
- Most everyday questions

3. **Low density content (basic query)**

LLMs prefer this when:
- Quick (short) answers
- Simple comparisons: "cheapest coffee delivery"
- Mobile or voice queries (people asking Siri/Alexa)

4.  **Keyword optimized content (strategic repetition)**

LLMs prefer this when:
- Brand-specific searches
- When competing with many similar services
- Building "entity recognition (helping LLMs understand what you are)

**Summary:**
When someone asks "What's the best coffee subscription?", the LLM has to:

1. Understand what information is most relevant
2. Pick from millions of web pages
3. Summarize in a helpful way

By testing different densities, we learn:

- High density might win for "how to choose coffee beans" queries
- Low density might win for "quick coffee delivery" queries
- Keyword-optimized might help LLMs remember the brand name

Let's say you're optimizing for the query: "best coffee subscription for beginners"

Test these variations:

1. High density: Include brewing guides, flavor wheel explanations, origin stories
2. Medium density: Focus on ease of use, variety packs, basic flavor descriptions
3. Low density: "Easy. Affordable. Delivered monthly. No coffee knowledge needed.
4. Keyword optimized: Repeat "beginner-friendly coffee subscription" naturally throughout

We should create all four versions and see which one ChatGPT, Claude, and Perplexity prefer to quote when answering that specific query. 

Need to do this on recurring basis because
1. Lacks industry wide systemic study
2. Change and upgrade (update) in model may change preference and format of responses
3. Query dependent preferences and responses

what we know so far is **claude** relies heavly on pretrained data (unless asked to conduct deep research query) and hence content optimization is challenging. Gemini does rely on traditional search (SEO formatted, PR articles and blogs).

## Key Questions

1. Why do identical queries produce different LLM responses? 
2. How to predict which content gets picked up by AI systems? (attribution challenge, citation landscape mapping) 
3. What triggers web search vs static response in ChatGPT? (freshness of data, relevance, pretraining data, create a system to identify web-search vs non-web-search prompts)
4. How to maintain accuracy while scaling automation? (dialing up/down on the number of prompts, frequency (daily/weekly) etc.

## Future Discussion

1. **LLM training data cut-offs**: How different LLMs have different training data cut-offs and update cycles. This fundamentally affects what content can be "optimized" for discovery
2. **RAG vs pre-training**: Optimizing for pre-training data (which is largely historical) versus optimizing for retrieval-augmented generation (RAG) systems that search the web in real-time
3. **Token context windows**: How LLMs process and prioritize information within their context windows, which is crucial for optimization
4. **Attribution challenge**: LLMs often don't provide consistent citations, making ROI measurement extremely difficult
---
*These insights compiled from internal research, customer interviews, and technical experimentation in the AI search optimization space by Kalyani Khona and Neuverge Labs Private Limited (https://neusearch.ai/).*
