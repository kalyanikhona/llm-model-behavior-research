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
1. **Accuracy over Features**: Trust metrics more important than feature count
2. **Transparency**: Show probability indicators for visibility confidence (with weekly update on improvement in the probabilities as we get thorough with research)
3. **Platform Approach**: Integration with existing SEO tools creates competitive advantage (multi agent system running GEO ops and optimisation)

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

## Key Unanswered Questions

1. Why do identical queries produce different LLM responses? 
2. How to predict which content gets picked up by AI systems? (attribution challenge, citation landscape mapping) 
3. What triggers web search vs static response in ChatGPT? (freshness of data, relevance, pretraining data, create a system to identify web-search vs non-web-search prompts)
4. How to maintain accuracy while scaling automation? (dialing up/down on the number of prompts, frequency (daily/weekly) etc.

## Future Discussion

1. **LLM Training Data Cut-offs**: How different LLMs have different training data cut-offs and update cycles. This fundamentally affects what content can be "optimized" for discovery
2. **RAG vs Pre-training**: Optimizing for pre-training data (which is largely historical) versus optimizing for retrieval-augmented generation (RAG) systems that search the web in real-time
3. **Token Context Windows**: How LLMs process and prioritize information within their context windows, which is crucial for optimization
4. **Attribution Challenge**: LLMs often don't provide consistent citations, making ROI measurement extremely difficult
---
*These insights compiled from internal research, customer interviews, and technical experimentation in the AI search optimization space by Kalyani Khona and Neuverge Labs Private Limited (https://neusearch.ai/).*
