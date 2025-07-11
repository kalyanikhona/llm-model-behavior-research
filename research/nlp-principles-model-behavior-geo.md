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
  
 ## 3. Frontier Lab Approaches 

### 3.1 What Fine-tuning Actually Does (NLP Perspective)

**Fine-tuning** is the process of taking a pre-trained model and teaching it specific behaviors through additional training on curated datasets. Think of it as "personality training" for AI.

**The NLP Pipeline:**
```
Raw Text → Pre-training (learn language) → Fine-tuning (learn behavior) → Your ChatGPT/Claude
```
Insight: Same base knowledge, different behavioral outputs based on fine-tuning approach.

### 3.2 The Four Major Approaches

#### **1. OpenAI (GPT Series) - The "Helpful Assistant" Approach**

**Fine-tuning Philosophy**: Maximum helpfulness, broad accessibility
- **RLHF Focus**: Reinforcement Learning from Human Feedback to be helpful
- **Training Data**: Diverse internet text + human demonstrations
- **Behavioral Traits**: 
  - Lists and structured responses
  - Tends to hedge less
  - More willing to speculate
  - Often provides multiple options
  - Quick, actionable answers rewarded
- **Attention Pattern Characteristics**:
  - Heads specialized for list detection
  - Strong attention to quantifiable benefits
  - Prefers scannable content structure

**GEO Implication**: OpenAI models favor content that offers choices and alternatives. They're trained to give users options. Optimize content with clear lists, comparisons, and multiple options. ChatGPT will synthesize structured content more readily.

#### **2. Anthropic (Claude) - The "Constitutional AI" Approach**

**Fine-tuning Philosophy**: Helpful, harmless, and honest (HHH)
- **Constitutional Training**: Models critique and revise their own outputs
- **Training Data**: More curated, academic sources + constitutional principles
- **Special Technique**: Trained on long documents with self-critique
- **Behavioral Traits**:
  - More cautious and thorough
  - Asks clarifying questions
  - Explicitly acknowledges uncertainty
  - Longer, more nuanced responses
  - Reasoning-focused attention patterns

**GEO Implication**: Claude favors authoritative, well-reasoned content with clear evidence. Academic and research-backed content performs better.

#### **3. Google (Gemini) - The "Multimodal Integration" Approach**

**Fine-tuning Philosophy**: Factual accuracy + multimodal understanding
- **Training Integration**: Leverages Google's vast data ecosystem
- **Special Focus**: Real-time information, visual understanding
- **Benchmark Optimization**: Factual accuracy benchmarks
- **Behavioral Traits**:
  - Emphasizes factual accuracy
  - Better at location-based queries
  - Integrates recent information more readily
  - More formal tone
  - Highest recency bias

**GEO Implication**: Gemini likely favors content that aligns with Google's E-E-A-T (experience, expertise, authoritativeness, trustworthiness) signals and freshness.

#### **4. Meta (LLaMA) - The "Open Research" Approach**

**Fine-tuning Philosophy**: Transparent, reproducible, community-driven
- **Open Approach**: Publicly documented training process
- **Base Models**: Others can fine-tune for specific uses
- **Variation Factor**: Different fine-tuners create vastly different behaviors
- **Behavioral Traits**:
  - More variable (depends on who fine-tuned it)
  - Often more technical/direct
  - Less "personality" in base form

**GEO Implication**: Different LLaMA variants may have completely different content preferences based on fine-tuning.

### 3.3 Technical Details 

#### **Instruction Tuning Differences**

Each lab uses different instruction datasets:

**OpenAI Example Instructions**:
```
"List the top 5 CRMs with pros and cons"
"Explain quantum computing simply"
"What are the best options for X?"
```

**Anthropic Example Instructions**:
```
"Help me understand which CRM fits my needs"
"Explain quantum computing, acknowledging what we don't know"
"What should I consider when choosing X?"
```

This is why ChatGPT loves lists while Claude prefers conversational exploration!

#### **RLHF Impact on Content Preference**

- **OpenAI's RLHF**: Rewards quick, useful answers → prefers scannable content
- **Anthropic's Constitutional**: Rewards thoughtfulness → prefers comprehensive content
- **Google's Approach**: Rewards factual accuracy → prefers cited, verifiable content

#### **Safety Training Variations**

- **OpenAI**: Broader acceptance, focuses on harmful content
- **Anthropic**: More conservative, focuses on honesty/uncertainty
- **Google**: Very conservative on facts, medical, financial advice

**GEO Impact**: Content that triggers safety filters on one model might be fine on another.

### 3.4 Hidden Ranking Factors Per Model

**OpenAI Models Prefer**:
- Structured content (lists, headers)
- Multiple options/alternatives
- Practical, actionable information
- Quantifiable benefits

**Anthropic Models Prefer**:
- Nuanced, thoughtful content
- Academic or research backing
- Content acknowledging complexity
- Causal reasoning ("because", "therefore")

**Google Models Prefer**:
- Authoritative sources
- Factually verifiable claims
- Recent, updated information
- E-E-A-T aligned content

### 3.5 Experiment Results: "How to Start a Podcast in 2025"

**ChatGPT Optimization**:
- Pros/cons lists
- Comparison charts for equipment/platforms
- Multiple options approach
- "2025" triggers web search insight
- Quick-start sections

**Claude Optimization**:
- Goal/objective exploration
- Clarifying questions approach
- Personalized difficulty levels
- Step-by-step guidance
- No auto-search on "2025"

**Gemini Optimization**:
- Authority/credibility focus
- Citation-heavy approach
- Multi-format content (videos)
- Strong disclaimers
- Explicit E-E-A-T optimization

### 3.6 Attention Mechanisms & Fine-tuning

#### **What is Attention?**

The mechanism that lets models understand which words are most important for understanding other words.

**Example**: "The bank by the river was full of people fishing"
- "bank" attends strongly to "river" and "fishing" → understands it's riverbank, not financial

#### **How Attention Works**

For every word, the model calculates:
1. **Query (Q)**: "What information do I need?"
2. **Key (K)**: "What information does each word offer?"
3. **Value (V)**: "What's the actual information?"

**Attention Score Formula** (simplified):
```
Attention(word1 to word2) = similarity(Q_word1, K_word2) × V_word2
```

#### **Multi-Head Attention**

Models have multiple attention "heads" looking for different patterns:
- **Head 1**: Company-product relationships (Apple → iPhone)
- **Head 2**: Action-object relationships (announced → iPhone)
- **Head 3**: Descriptive relationships (new → iPhone)

#### **How Fine-tuning Shapes Attention**

**Base Model**: General attention patterns
**After OpenAI Fine-tuning**: 
- Heads specialized for listing items
- Strong attention: "best" → multiple following items

**After Anthropic Fine-tuning**:
- Heads specialized for reasoning chains
- Strong attention: "because" → evidence

#### **Practical Impact for GEO**

**Content for ChatGPT's Attention Pattern**:
```
❌ "Our CRM helps businesses grow through intelligent automation"
✅ "Our CRM offers: • 50+ integrations • AI automation • Real-time analytics"
```

**Content for Claude's Attention Pattern**:
```
❌ "The best CRM with amazing features"
✅ "Our CRM reduces manual work by 70% because it automates repetitive tasks"
```

### 3.7 Attention + Web Search Synthesis

When models search and synthesize:

1. **Query Understanding**: Attention identifies key concepts
2. **Search Processing**: Scans results for matching attention patterns
3. **Synthesis**: Combines info based on learned preferences

**GEO Insight**: Optimizing for attention patterns, not keywords!

### 3.8 Other Important Notes

1. **Token Economics**: Claude handles long docs better due to attention efficiency from constitutional self-critique training, not just context size

2. **Citation Trust Patterns**: Based on source distribution in fine-tuning:
   - OpenAI: More Reddit/forum trust (marked "helpful")
   - Anthropic: More academic trust (marked "truthful")
   - Google: More authoritative media trust (quality signals)

3. **Certainty Expression**: 
   - GPT-4: "The best option is likely..."
   - Claude: "Based on available information..."
   - Gemini: "According to [source]..."

4. **Benchmark Influence**:
   - OpenAI: User satisfaction metrics
   - Anthropic: Truthfulness benchmarks
   - Google: Factual accuracy benchmarks


### 3.9 Advanced GEO Strategies

1. **For OpenAI Models**: Structure content for list-attention patterns
2. **For Anthropic Models**: Build reasoning chains with clear causality
3. **For Google Models**: Emphasize verifiable facts with authority signals
4. **For All Models**: Place related concepts where attention will connect them
   
Important: Focus on optimizing for **learned attention patterns** shaped by each lab's fine-tuning philosophy, **not algorithms**

 ---

## 7. Key Learnings 

1. **Modern AI search is a hybrid system** - combining traditional web crawling with LLM synthesis
2. **Semantic understanding > keyword matching** - Focus on meaning and context
3. **Different models = different biases** - Training data composition affects brand representation
4. **Tokenization matters** - How your brand name is broken down affects recognition
5. **Dual optimization needed** - Must optimize for both crawling and synthesis layers
6. **Pre-training bias is stronger than web search** - Established brands have semantic monopoly
7. **Content structure affects synthesis** - Clear structure = higher confidence = better visibility
8. **New brands need different strategies** - Can't compete head-on with semantic monopolies
9. **Web search confirms more than discovers** - Acts as validation layer, not discovery layer
10. **Future-proofing matters** - Optimize for next generation model training, not just current search
11. **Fine-tuning creates personality** - Same knowledge base, different behavioral outputs
12. **Attention mechanisms are shaped by fine-tuning** - Models literally "see" content differently
13. **Each lab optimizes for different goals** - User satisfaction vs truthfulness vs accuracy
14. **Content optimization must be model-specific** - One size does not fit all
15. **Hidden biases from training data** - Source distribution affects trust patterns
16. **Technical constraints matter** - Context windows, instruction templates affect processing
17. **Different fine-tuning = Different content preferences** at the attention level
18. **Instruction templates shape behavior** more than most realize
19. **RLHF rewards create implicit biases** in content selection
20. **Attention patterns determine** what gets synthesized
21. **Model-specific optimization required** - no universal approach


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
