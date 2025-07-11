# NLP Principles for Model Behavior Research & GEO Strategy

Document Type: Planning Notes
Date: July 11, 2025
Focus: NLP, Frontier model, LLM architecture, user behaviour, prompting patterns

---

## Table of Contents
1. [Core NLP Concepts & LLM Architecture](#1-core-nlp-concepts--llm-architecture)
2. [How Models Process & Rank Content](#2-how-models-process--rank-content)
3. [Frontier Lab Approaches to Fine-tuning](#3-frontier-lab-approaches)
4. [Content Visibility & LLM Preferences](#4-content-visibility)
5. [User Behavior & Prompting Patterns](#5-user-behavior)
6. [Practical Applications for GEO](#6-practical-applications)
7. [Key Learnings & Action Items](#7-key-learnings)

---

## 1. Core NLP Concepts & LLM Architecture

### 1.1 From Keywords to Semantics

**Traditional Search (Google):**
- Crawls web pages in real-time
- Indexes keywords and metadata
- Uses PageRank and hundreds of ranking signals
- Matches query keywords to document keywords
- Returns links for users to explore

**Pure LLMs (Base Models):**
- Pre-trained on massive text corpora (knowledge frozen at training cutoff)
- Understand context and meaning (semantics)
- Generate responses based on patterns learned
- No real-time crawling - cannot access information after training
- Synthesize and create narrative responses

**Hybrid LLMs (ChatGPT with web search, Claude with search, Perplexity):**
- Combines both approaches:
  ```
  User Query → LLM decides if search needed → Web Search → 
  Raw results → LLM processes/synthesizes → Formatted response
  ```
- 30% traditional search (finding the right pages)
- 70% LLM synthesis (understanding, filtering, formatting)

### 1.2 How LLMs Actually "See" Text

**Tokenization Process:**
- Break words into smaller pieces (tokens)
- Convert these pieces into numbers (embeddings)
- Analyze relationships between tokens across millions of examples

**Example:**
- Input: "How to optimize content for AI"
- Tokens: ["How", " to", " optim", "ize", " content", " for", " AI"]
- Each token → 768-4096 dimensional vector (depending on model)

**💡 GEO Insight #1:** Unlike SEO where exact keywords matter, LLMs care about semantic meaning. 
"Optimize for AI" ≈ "Make content AI-friendly" ≈ "Improve content for machine learning models"

### 1.3 The Citation and Content Discovery Problem

**Key Challenge:** LLMs don't "search" or "cite" in the traditional sense - they're pattern completion machines that have learned statistical relationships.

**Comparison:**
- **Google**: Has a live index, can point to specific URLs, knows where information comes from
- **Base LLMs**: Have "absorbed" information into their weights, like a student who studied thousands of textbooks but can't remember which book taught them what
- **LLMs + Web Search**: Can now cite sources, but synthesis is still influenced by pre-training

### 1.4 Training Data Differences Across Frontier Labs

**Why Different Models Handle Brand Mentions Differently:**

1. **OpenAI's GPT Series:**
   - Heavy on internet text, Reddit, news articles
   - Strong representation of Western, English-language content
   - Likely includes Wikipedia, academic papers, coding repositories

2. **Anthropic's Claude:**
   - More curated, academic sources
   - Constitutional AI training for helpfulness and harmlessness
   - Potentially more balanced global perspective

3. **Google's Gemini:**
   - Likely more diverse, multilingual training data
   - Access to Google's vast web index during training
   - Potential YouTube transcripts and Google Books

4. **Meta's LLaMA:**
   - Open-source data, more transparent about sources
   - CommonCrawl, Wikipedia, books, academic papers
   - Can be fine-tuned by anyone for specific use cases

### 1.5 Technical Foundations

**Attention Mechanism**
- Models learn which words/concepts are most important for understanding other words
- Example: "The CEO of **Apple** announced a new **iPhone**" 
  - Model learns strong relationship between "Apple" and "iPhone"
  - Context "CEO" and "announced" help disambiguate from fruit

**Tokenization Impact on Brand Recognition:**
- "McDonald's" might be tokenized as ["Mc", "Donald", "'s"] or ["McDonald", "'s"]
- This affects how well models recognize and generate brand content
- Newer brands or unique names might be split into unexpected tokens

### 1.6 The Web Search Revolution in LLMs

**Dual Optimization Required**

When optimizing for modern AI systems, you're now optimizing for:
1. **The web crawler component** (similar to Google bot) - Still needs traditional SEO
2. **The LLM synthesizer** - Needs content structured for AI comprehension

**Real Example Test Case:**
- Q: "If a brand new company launched yesterday, how would ChatGPT with web search talk about it differently than ChatGPT without web search?"
- A: ChatGPT without web search wouldn't know about it at all (knowledge cutoff)
- A: ChatGPT with web search could crawl the company's website, Reddit discussions, social media, and news mentions to provide current information

**Key Insight:** The LLM doesn't just compile search results - it interprets them through pre-trained understanding, filters based on training biases, and reformats according to fine-tuning preferences.

---

## 2. How Models Process & Rank Content

### 2.1 The Hidden Ranking System in LLMs

Unlike Google's PageRank algorithm, LLMs don't have traditional "ranking" - they have **"Preference Patterns"** from training:

**Comparison:**
- **Google**: "This page has 1000 backlinks, it must be authoritative"
- **LLMs**: "In my training, when people discussed [topic], they usually referenced these sources"

### 2.2 The Three Layers of Content Processing

When LLM + web search processes queries:

1. **Relevance Layer** (Traditional SEO matters)
   - Web search finds pages with relevant keywords
   - Similar to Google's initial crawl

2. **Comprehension Layer** (New for GEO)
   - Can the LLM easily extract information?
   - Is content structure AI-friendly?
   - Are concepts clearly defined with context?

3. **Synthesis Preference Layer** (The secret sauce)
   - Which information aligns with model's training patterns?
   - What content structure does it prefer to cite?
   - How does it weight different source types?

### 2.3 Experiment: CRM Recommendations Across Models

**Test Query**: "What are the top 3 CRM solutions for small businesses?"

**Results Summary:**
- ChatGPT (no search): HubSpot, Zoho, Pipedrive
- ChatGPT (with search): HubSpot, Zoho, Pipedrive (added citations)
- Claude (with search): HubSpot, Salesforce, Pipedrive
- Claude (no search): HubSpot, Salesforce, Pipedrive

**Key Finding**: Web search didn't change core recommendations - only added validation/pricing

### 2.4 Why Pre-training Dominates Over Web Search

#### The Confirmation Bias Loop:
```
Pre-trained bias: "HubSpot is good for small business"
↓
Searches web → Finds articles mentioning HubSpot
↓
Confirms bias → Outputs HubSpot
```

#### Semantic Monopoly:
Certain brands achieved deep association with queries during training period (2019-2024):
- "CRM" → HubSpot, Salesforce
- "Spreadsheet" → Excel
- "Video conferencing" → Zoom

### 2.5 Why AI-Friendly Content Structure Matters

**Common Misconception**: "LLMs can process any content format"

**Reality**: Processing ability ≠ Processing preference

#### Example - Messy vs Clean Structure:
```html
<!-- Messy (Low confidence extraction) -->
<div>Our pricing starts at just $15!</div>
<span>per user</span>
<p>monthly if billed annually</p>

<!-- AI-Friendly (High confidence extraction) -->
<div class="pricing">
  <h3>Pricing</h3>
  <p>$15 per user per month (billed annually)</p>
</div>
```

**Impact**: 
- Clear structure = Higher confidence score = More likely to be synthesized
- Ambiguous structure = More compute needed = May be ignored

### 2.6 Breaking Into AI Responses - Complete Strategy

For new brands to appear in AI responses:

1. **High-quality comparison content** ✓
2. **Crawlable for future training data** ✓
3. **Traditional SEO optimization** ✓
4. **Semantic Positioning Strategy**
   - Target: "CRM for [specific niche]" not generic "best CRM"
   - Own unique semantic space

5. **Wikipedia/Reddit Strategy**
   - These sources heavily weighted in training
   - Need authentic, organic mentions

6. **Structured Data Markup**
   ```json
   {
     "@type": "SoftwareApplication",
     "name": "YourCRM",
     "applicationCategory": "CRM",
     "offers": {
       "@type": "Offer",
       "price": "15.00"
     }
   }
   ```

7. **Anti-Pattern Content**
   - "Why X is different from HubSpot"
   - "When NOT to use traditional CRMs"
   - Forces models to mention you as alternative

8. **Fresh Signal Optimization**
   - Weekly updates/changelog
   - Regular publishing rhythm
   - User-generated content

---

## Key Learnings So Far

1. **Modern AI search is a hybrid system** - combining traditional web crawling with LLM synthesis
2. **Semantic understanding > keyword matching** - Focus on meaning and context
3. **Different models = different biases** - Training data composition affects brand representation
4. **Tokenization matters** - How your brand name is broken down affects recognition
5. **Dual optimization needed** - Must optimize for both crawling and synthesis layers
6. **Pre-training bias is stronger than web search** - Established brands have semantic monopoly
2. **Content structure affects synthesis** - Clear structure = higher confidence = better visibility
3. **New brands need different strategies** - Can't compete head-on with semantic monopolies
4. **Web search confirms more than discovers** - Acts as validation layer, not discovery layer
5. **Future-proofing matters** - Optimize for next generation model training, not just current search


---

## Questions for Further Exploration

- How do users actually interact with AI chatbots vs traditional search?
- What prompting patterns are most common among mainstream users?
- How can brands ensure consistent representation across different LLM platforms?
- What content structures work best for AI comprehension and synthesis?

---

## Next Topics to Cover

- Detailed analysis of how models rank and prioritize content
- User behavior studies and prompting patterns
- Practical GEO optimization strategies
- Frontier lab fine-tuning methodologies
---
