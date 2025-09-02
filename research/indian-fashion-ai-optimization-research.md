# AI Visibility Fashion Brands: Indian Market Analysis

![Research Status](https://img.shields.io/badge/Status-Ongoing%20Research-orange?style=flat-square)
![Start Date](https://img.shields.io/badge/Start%20Date-Sept%202,%202025-blue?style=flat-square)
![Document Type](https://img.shields.io/badge/Type-Living%20Document-green?style=flat-square)
![Author](https://img.shields.io/badge/Author-[Kalyani Khona]-purple?style=flat-square)

## Project Overview
**Objective**: Analyze how Indian users prompt fashion queries on ChatGPT and identify optimization opportunities for D2C fashion brands.

---

## Phase 1: Brand AI Response Analysis

### Task 1: Brand Selection & Query Generation

#### Step 1.1: Brand List Creation
**Tool**: Claude/Perplexity
**Prompt**: 

1. Generate 20 top Indian D2C fashion brands with URLs, categorized as: 5 ethnic wear, 5 western wear, 5 accessories, 5 sustainable/indie brands.
2. Include brand name, URL, and primary category.
3. Customise this as per linguistic patterns mapped in my personal dataset of real unsantisied prompts

#### Step 1.2: Query Set Development
**Method**: Separate Claude conversation with your 200 real Indian prompts
- Upload your non-fashion prompt data to Claude
- Extract linguistic patterns: average word count, code-switching frequency, price mention patterns
- Generate 20 fashion-specific queries reflecting these patterns

We need to become really good at this step and it makes all the difference to the quality and accuracy of the research because

1. Measuring visibility inside LLM outputs is challenging for several reasons
2. LLM answers are non-deterministic and increasingly personalized by chat history, location, device, and preferences.
3. Each LLM is built differently, so citations and answer styles vary across tools.
4. Answers also evolve over time as new models are announced.
5. Chat interfaces are inconsistent: some LLMs add footnote sources, others provide in-line links, some paraphrase information without a link, and many rotate sources between refreshes.

**Query Categories** (4 prompts each):
- **Occasion-based**: Wedding, office, party, casual, festival
- **Price-sensitive**: Under ₹1000, ₹1000-3000, ₹3000-5000, ₹5000+ 
- **Cultural-specific**: Traditional + modern fusion, regional preferences
- **Seasonal**: Summer, monsoon, winter, festival season
- **Code-switching examples**: Mix of English-Hindi-regional languages

#### Step 1.3: Automated Testing Setup
**Tool**: Neusearch.ai service
1. Create CSV with 400 combinations (20 brands × 20 queries)
2. Upload to NS service
3. Collect ChatGPT responses + web search trigger data

### Task 2: Neusearch Tool Integration

#### Step 2.1: Brand URL Analysis
**Process**:
1. Input all 20 brand URLs into Neusearch
2. Run 10-15 standardized fashion queries per brand
3. **Track metrics**:
   - Mention frequency
   - Context quality (positive/neutral/negative)
   - Search trigger rate
   - **Sentiment analysis**
   - Response relevance score

#### Step 2.2: Output
**Output**: Individual brand analysis report
**Template**:
- Brand AI visibility score
- Top triggers for brand mentions
- Content gaps identified
- Optimization recommendations
- Competitive positioning

### Task 3: AI Optimization Documentation

#### Step 3.1: Website Content Analysis (check with Ankit on this)
**Screaming Frog Overview**: SEO crawler that extracts all website content (meta descriptions, headings, page structure, internal links). 
**Process**:
1. Crawl each brand's website with Screaming Frog
2. Export content data (titles, descriptions, product names)
3. Feed to ChatGPT with prompt: "Analyze this content for AI-friendliness. Score 1-10 for: clarity, keyword optimization, cultural relevance, AI comprehension."

#### Step 3.2: AI-Friendly Content Analysis
**Tool**: Claude with standardized framework
**Prompt Template**:
```
Analyze this brand's content for AI optimization:
[Brand content]

Rate 1-10 on:
1. Natural language clarity
2. Cultural context inclusion
3. Occasion-specific language
4. Price transparency
5. Regional relevance

Provide specific improvement recommendations.
```

#### Step 3.3: Manual Spot Checks
**Workflow**:
1. Test 5 obvious brand queries per category:
   - "Best [category] brands in India"
   - "[Category] under ₹2000"
   - "Indian [category] for [occasion]"
2. Document: mentioned vs not mentioned + reasoning
3. Cross-reference with brand content quality scores

---

## Enhanced Analysis Framework

### "Why" Analysis Components

#### What Makes Brands AI-Favored?
**Tracking Method**:
- **Content structure analysis**: H1/H2 usage, product descriptions, about pages
- **Cultural relevance scoring**: Festival mentions, regional references, family context
- **Technical factors**: Site speed, mobile optimization, structured data

#### Content Patterns That Trigger Mentions
**Measurement Strategy**:
- Compare mentioned vs non-mentioned brands' content
- Identify common phrases/structures in successful brands
- Map correlation between content elements and AI visibility

#### Online Presence Structure Analysis
**Key Metrics**:
- **Content freshness**: Blog update frequency, new product launches
- **SEO foundation**: Meta descriptions, alt text, schema markup
- **Social proof integration**: Reviews, testimonials, user-generated content
- **Cultural integration**: Festival collections, regional preferences, price transparency

---

## Streamlined Workflow Summary

### Data Collection
- Generate brand list + query set with linguistic patterns
- Run NeuSearch scan + analysis
- Screaming Frog crawls + content analysis

### Analysis & Insights
- Julius AI analysis of all collected data
- Pattern identification + "why" analysis
- Framework development + case studies
---

## Tools 

| Task | Primary Tool | Alternative | Output Format |
|------|-------------|-------------|---------------|
| Brand Research | Claude/Perplexity | Manual research | CSV list |
| Query Testing | Neusearch temporary tool | Manual testing | CSV responses |
| Brand URL Analysis | NeuSearch | Manual queries | Structured data |
| Content Crawling | Screaming Frog | Manual collection | Export files |
| Data Analysis | Julius AI | Claude Artifacts | Insights report |
| Content Analysis | Claude | ChatGPT | Scoring framework |

---
