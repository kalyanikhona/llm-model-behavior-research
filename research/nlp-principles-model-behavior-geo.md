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
  
  ## 3. Frontier Lab Approaches to Fine-tuning

### 3.1 What Fine-tuning Actually Does (NLP Perspective)

**Fine-tuning** = The process of taking a pre-trained model and teaching it specific behaviors through additional training on curated datasets. Think of it as "personality training" for AI.

**The NLP Pipeline:**
```
Raw Text → Pre-training (learn language) → Fine-tuning (learn behavior) → Your ChatGPT/Claude
```

**Key Insight**: Same base knowledge, different behavioral outputs based on fine-tuning approach.

### 3.2 The Four Major Approaches

#### **1. OpenAI (GPT Series) - The "Helpful Assistant" Approach**

**Fine-tuning Philosophy**: Maximum helpfulness, broad accessibility

**Technical Implementation**:
- **RLHF Focus**: Reinforcement Learning from Human Feedback optimized for user satisfaction
- **Training Data**: Diverse internet text + human demonstrations of helpful responses
- **Reward Model**: Optimizes for quick, useful answers

**Behavioral Traits**:
- Lists and structured responses preferred
- Multiple options/alternatives given
- Less hedging, more direct recommendations
- "Quick start" mentality

**Attention Pattern Characteristics**:
- Heads specialized for list detection
- Strong attention to quantifiable benefits
- Prefers scannable content structure

**GEO Implication**: Optimize content with clear lists, comparisons, and multiple options. ChatGPT will synthesize structured content more readily.

#### **2. Anthropic (Claude) - The "Constitutional AI" Approach**

**Fine-tuning Philosophy**: Helpful, Harmless, and Honest (HHH)

**Technical Implementation**:
- **Constitutional Training**: Models critique and revise their own outputs
- **Training Data**: Curated academic sources + constitutional principles
- **Self-Critique Loop**: Trains on long documents analyzing its own responses

**Behavioral Traits**:
- Asks clarifying questions before assuming
- Acknowledges uncertainty explicitly
- Longer, more nuanced responses
- Reasoning-first approach

**Attention Pattern Characteristics**:
- Heads specialized for causal relationships
- High attention to "because," "therefore," "evidence"
- Better long-document coherence

**GEO Implication**: Optimize content with clear reasoning, evidence, and nuanced explanations. Claude favors thoughtful, well-supported content.

#### **3. Google (Gemini) - The "Multimodal Integration" Approach**

**Fine-tuning Philosophy**: Factual accuracy + real-world grounding

**Technical Implementation**:
- **Training Integration**: Leverages Google's search quality signals
- **E-E-A-T Alignment**: Optimized for Experience, Expertise, Authoritativeness, Trustworthiness
- **Freshness Bias**: Highest among all models

**Behavioral Traits**:
- Emphasizes source credibility
- Stronger disclaimers on YMYL topics
- Prefers recent information
- More formal, encyclopedic tone

**Attention Pattern Characteristics**:
- Heads tuned to authority signals
- High attention to citations and sources
- Temporal attention (dates, "latest," "2025")

**GEO Implication**: Optimize for traditional SEO signals + freshness. Gemini trusts established, recently-updated sources.

#### **4. Meta (LLaMA) - The "Open Research" Approach**

**Fine-tuning Philosophy**: Base model for community adaptation

**Technical Implementation**:
- **Minimal Fine-tuning**: Base model is less opinionated
- **Open Architecture**: Allows custom fine-tuning
- **Variable Implementations**: Each variant can be completely different

**Behavioral Traits**:
- More direct, less "personality"
- Technical/academic tone in base form
- Highly variable based on who fine-tunes

**GEO Implication**: Must understand specific variant. No universal LLaMA optimization strategy.

### 3.3 Deep Dive: Attention Mechanisms and Fine-tuning

#### Understanding Attention (Simple Version)

**Attention** = How AI decides which words to "look at" when understanding other words

Example: "The bank by the river was full of people fishing"
- "bank" pays high attention to → "river," "fishing" (context)
- Result: AI understands "bank" = riverbank, not financial institution

#### How Attention Works Technically

**Three Components (Q, K, V)**:
```
For each word:
- Query (Q): "What information do I need?"
- Key (K): "What information does each word offer?"
- Value (V): "What's the actual information?"
```

**Attention Score Calculation**:
```
Word "iPhone" in "Apple announced a new iPhone":
- iPhone → Apple: 0.8 (high attention)
- iPhone → announced: 0.3 (medium attention)
- iPhone → new: 0.4 (medium attention)
```

#### Multi-Head Attention - The Game Changer

LLMs have multiple "attention heads" looking for different patterns:

**Example Heads**:
- Head 1: Company-product relationships (Apple → iPhone)
- Head 2: Action-object relationships (announced → iPhone)
- Head 3: Descriptive relationships (new → iPhone)

#### How Fine-tuning Shapes Attention

**Base Model**: General attention patterns
**After Fine-tuning**: Specialized attention patterns

**OpenAI Fine-tuning Effect**:
```
"Best" → [strong attention] → quantifiable features
"Options" → [strong attention] → list items
Result: Prefers bulleted lists, comparisons
```

**Anthropic Fine-tuning Effect**:
```
"Because" → [strong attention] → reasoning chain
"However" → [strong attention] → nuance/caveats
Result: Prefers explanatory content
```

### 3.4 Real-World Testing and Behavioral Differences

#### Experiment: "How to start a podcast in 2025"

**ChatGPT Optimization**:
- Structure: Lists, comparison charts, quick-start guides
- Features: Platform comparisons, equipment tables
- Tone: Direct recommendations
- 2025 mention triggers web search for fresh content

**Claude Optimization**:
- Structure: Goal exploration → personalized guidance
- Features: Why → What → How progression
- Tone: Conversational, acknowledging complexity
- Less likely to auto-search on "2025"

**Gemini Optimization**:
- Structure: Authoritative sections with citations
- Features: Expert quotes, success metrics
- Tone: Professional, fact-based
- Highest weight on 2025 content

### 3.5 Hidden Factors in Fine-tuning

#### 1. **Training Data Source Distribution**

**Why it matters**: Creates trust biases
- OpenAI + Reddit → trusts user-generated content
- Anthropic + Academic → trusts scholarly sources
- Google + Web index → trusts established websites

#### 2. **Benchmark Optimization**

Each lab optimizes for different metrics:
- OpenAI: User satisfaction scores
- Anthropic: Truthfulness benchmarks
- Google: Factual accuracy tests

This creates hidden content preferences!

#### 3. **Context Window Utilization**

Fine-tuning affects how models use their context:
- GPT: Optimized for shorter, punchy content
- Claude: Optimized for long-form analysis
- Gemini: Balanced approach

#### 4. **Instruction Template Impact**

Different templates create different parsing strategies:
```python
# OpenAI style
"System: You are a helpful assistant"
→ Expects direct questions/answers

# Anthropic style  
"Human: [question]\nAssistant: [thoughtful response]"
→ Expects conversational flow
```

### 3.6 Advanced GEO Strategies Based on Fine-tuning

#### Content Structure by Model

**For OpenAI Models**:
```markdown
# Topic (Clear H1)
## Quick Overview (Bullet points)
## Detailed Sections
- Option 1: Pros/Cons
- Option 2: Pros/Cons
## Comparison Table
## Quick Start Guide
```

**For Anthropic Models**:
```markdown
# Understanding [Topic]
## Why This Matters
## Core Concepts Explained
Because [reasoning], we can see that...
## Evidence and Research
Studies show... However, it's important to note...
## Practical Applications
```

**For Google Models**:
```markdown
# [Topic]: Expert Guide 2025
*Last updated: [Date]*
*By: [Credentialed Author]*
## Overview (with citations)
## Detailed Sections
According to [Authority Source]...
## External References
```

### 3.7 Practical Takeaways for GEO

**The Paradigm Shift**: You're not optimizing for algorithms anymore - you're optimizing for attention patterns shaped by fine-tuning.

**Model-Specific Optimization**:
- ChatGPT: Optimize for utility and quick scanning
- Claude: Optimize for reasoning and depth
- Gemini: Optimize for authority and freshness
- LLaMA variants: Research specific implementation

**Content Features by Model Preference**:
| Feature | ChatGPT | Claude | Gemini |
|---------|---------|---------|---------|
| Lists/Bullets | ⭐⭐⭐ | ⭐ | ⭐⭐ |
| Long reasoning | ⭐ | ⭐⭐⭐ | ⭐⭐ |
| Citations | ⭐⭐ | ⭐⭐ | ⭐⭐⭐ |
| Recent dates | ⭐⭐ | ⭐ | ⭐⭐⭐ |
| Comparisons | ⭐⭐⭐ | ⭐⭐ | ⭐⭐ |

### 3.9 Testing Your Understanding

**Experiment Results from User Testing**:
- Correctly identified ChatGPT's preference for lists and web search triggers
- Understood Claude's conversational, goal-first approach
- Recognized Gemini's authority and citation focus
- Grasped that LLaMA variants depend on specific fine-tuning

**Knowledge Gaps Identified and Addressed**:
1. Technical mechanisms behind behavioral differences ✓
2. Attention mechanism understanding ✓
3. How fine-tuning affects content trust ✓
4. Why same content ranks differently across models ✓

---

# 7-key-learnings

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
