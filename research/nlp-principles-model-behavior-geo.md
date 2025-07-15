# NLP Principles for Model Behavior Research & GEO Strategy

- Document Type: Planning Notes
- Date: July 11, 2025
- Focus: NLP, Frontier model, LLM architecture, user behaviour, prompting patterns

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
-**Attention Pattern Characteristics**:
  - Heads specialized for causal relationships
  - High attention to "because," "therefore," "evidence"
  - Better long-document coherence

**GEO Implication**: Claude favors authoritative, well-reasoned content with clear evidence. Academic and research-backed content performs better. Optimize content with clear reasoning, evidence, and nuanced explanations. 

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
 - **Attention Pattern Characteristics**:
  - Heads tuned to authority signals
  - High attention to citations and sources
  - Temporal attention (dates, "latest," "2025")

**GEO Implication**: Gemini likely favors content that aligns with Google's E-E-A-T (experience, expertise, authoritativeness, trustworthiness) signals and freshness. Optimize for traditional SEO signals. Gemini trusts established, recently-updated sources.

#### **4. Meta (LLaMA) - The "Open Research" Approach**

**Fine-tuning Philosophy**: Transparent, reproducible, community-driven
- **Open Approach**: Publicly documented training process
- **Base Models**: Others can fine-tune for specific uses
- **Variation Factor**: Different fine-tuners create vastly different behaviors
- **Behavioral Traits**:
  - More variable (depends on who fine-tuned it)
  - Often more technical/direct
  - Less "personality" in base form

**GEO Implication**: Must understand specific variant. No universal LLaMA optimization strategy. Different LLaMA variants may have completely different content preferences based on fine-tuning.

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
- Structure: Lists, comparison charts, quick-start guides
- Features: Platform comparisons, equipment tables
- Tone: Direct recommendations
- 2025 mention triggers web search for fresh content

**Claude Optimization**:
- Goal/objective exploration
- Clarifying questions approach
- Personalized difficulty levels
- Step-by-step guidance
- Structure: Goal exploration → personalized guidance
- Features: Why → What → How progression
- Tone: Conversational, acknowledging complexity
- Less likely to auto-search on "2025"

**Gemini Optimization**:
- Authority/credibility focus
- Citation-heavy approach
- Multi-format content (videos)
- Strong disclaimers
- Explicit E-E-A-T optimization
- Structure: Authoritative sections with citations
- Features: Expert quotes, success metrics
- Tone: Professional, fact-based
- Highest weight on 2025 content

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

2. **Citation Trust Patterns/Training Data Source Distribution**
   - OpenAI: More Reddit/forum trust (marked "helpful") → trusts user-generated conten
   - Anthropic: More academic trust (marked "truthful") → trusts scholarly sources
   - Google: More authoritative media trust (quality signals) → trusts established websites

3. **Certainty Expression**: 
   - GPT-4: "The best option is likely..."
   - Claude: "Based on available information..."
   - Gemini: "According to [source]..."

4. **Benchmark Influence**:
   - OpenAI: User satisfaction score
   - Anthropic: Truthfulness benchmarks
   - Google: Factual accuracy benchmarks
  
5. **Context Window Utilization**:
   - Fine-tuning affects how models use their context:
   - GPT: Optimized for shorter, punchy content
   - Claude: Optimized for long-form analysis
   - Gemini: Balanced approach


### 3.9 Advanced GEO Strategies

1. **For OpenAI Models**: Structure content for list-attention patterns
2. **For Anthropic Models**: Build reasoning chains with clear causality
3. **For Google Models**: Emphasize verifiable facts with authority signals
4. **For All Models**: Place related concepts where attention will connect them

Content structure by model:

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

Important: Focus on optimizing for **learned attention patterns** shaped by each lab's fine-tuning philosophy, **not algorithms**

Summary

**Content Features by Model Preference**:
| Feature | ChatGPT | Claude | Gemini |
|---------|---------|---------|---------|
| Lists/Bullets | ⭐⭐⭐ | ⭐ | ⭐⭐ |
| Long reasoning | ⭐ | ⭐⭐⭐ | ⭐⭐ |
| Citations | ⭐⭐ | ⭐⭐ | ⭐⭐⭐ |
| Recent dates | ⭐⭐ | ⭐ | ⭐⭐⭐ |
| Comparisons | ⭐⭐⭐ | ⭐⭐ | ⭐⭐ |

 ---
 
## 4. Content Visibility

### 4.1 Query Intent Trumps General Preferences

**Scenario**: Two articles about "AI writing tools":

**Article A**: 
- 2000 words, comprehensive history of AI writing
- Academic tone, lots of citations
- Published on university blog
- No clear structure, long paragraphs

**Article B**:
- 800 words, "Top 5 AI Writing Tools 2025"
- Scannable format with H2s, bullets
- Published on marketing blog
- Clear comparisons, pricing info

**Analysis**: For query "What are the best AI writing tools?" - Both ChatGPT and Claude would synthesize Article B more heavily.

**Key Learning**: Query intent trumps general preferences. Academic content wins for research queries, structured lists win for recommendation queries.

### 4.2 Layers of Content Discovery

- Content must pass through multiple filters to be synthesized. 
- Content can fail at ANY layer and become invisible. 
- Perfect SEO (Layer 1) means nothing if you fail at Layer 4 (Efficiency).

```
Layer 1: Crawlability
├─ Is the page accessible to web crawlers?
├─ Proper robots.txt configuration?
└─ Fast loading time?

Layer 2: Parsability  
├─ Clear HTML structure?
├─ Semantic markup?
└─ Readable text extraction?

Layer 3: Relevance
├─ Query-content alignment?
├─ Semantic similarity?
└─ Intent matching?

Layer 4: Efficiency
├─ Information density?
├─ Clear extraction points?
└─ Minimal processing needed?

Layer 5: Confidence
├─ Authoritative signals?
├─ Factual consistency?
└─ Recent/updated content?

Layer 6: Synthesis Priority
├─ Fits response format?
├─ Adds unique value?
└─ Computational ROI?
```

### 4.3 Computational Preference Patterns

#### The Processing Cost Hierarchy

LLMs have finite computational budgets. They naturally prefer content with lower processing costs:

**Lowest Cost (Highest Preference)**:
```markdown
## Clear Header Matching Query
- Bullet point with key information
- Second bullet with specific detail
- **Bold** emphasis on important terms
```

**Medium Cost**:
```markdown
This paragraph contains relevant information about the topic, 
though it requires parsing through multiple sentences to extract 
the key points that answer the user's question.
```

**Highest Cost (Lowest Preference)**:
```markdown
It was in the context of examining various solutions, while 
considering multiple factors that had been previously discussed 
in the literature, that we came to understand that certain 
approaches, which had been suggested by researchers whose work 
we cited earlier, might potentially offer benefits.
```

#### Impact

When processing 10 search results in 200ms, LLMs will:
1. Quick-scan all 10 for structure
2. Deep-process 3-4 most efficient sources
3. Light-skim remaining sources
4. Synthesize primarily from efficient sources

### 4.4 Semantic Density Optimization

**Semantic Density** = Information value per token

#### High Semantic Density Example:
```
"GPT-4: $20/month, 128k context, SOTA performance, API access included"
```
- 11 tokens conveying 4 key facts
- Density: 0.36 facts/token

#### Low Semantic Density Example:
```
"When considering GPT-4, it's important to note that the pricing 
structure has been set at twenty dollars per month, and users will 
find that it offers a context window of 128,000 tokens"
```
- 38 tokens conveying same 4 facts
- Density: 0.10 facts/token

**LLMs strongly prefer high semantic density content for synthesis**

#### Optimizing Content for High Density

1. **Front-load key information**
   ```
   ❌ "After extensive research, we found that..."
   ✅ "Key finding: X improves Y by 47%"
   ```

2. **Use precise numbers over vague descriptors**
   ```
   ❌ "Significantly improves performance"
   ✅ "Improves performance by 3.2x"
   ```

3. **Structured data over prose**
   ```
   ❌ Paragraph describing features
   ✅ Feature comparison table
   ```

### 4.5 The Citation Probability Framework

What makes content "quotable" by LLMs? 
Content must be:

#### 1. **Distinctive**
- Unique insights not found elsewhere
- Specific data points or statistics
- Clear stance or recommendation

#### 2. **Self-contained**
- Complete thoughts in single sentences
- No pronouns requiring external context
- Clear subject-verb-object structure

#### 3. **Authoritative**
- From recognized source
- Contains supporting evidence
- Recent and relevant

#### Citation Probability Formula (Simplified):
```
P(citation) = Distinctiveness × Clarity × Authority × Relevance
```

#### Examples:

**High Citation Probability**:
"According to Stanford's 2025 AI Index, enterprise LLM adoption reached 67%, up from 23% in 2023."

**Low Citation Probability**:
"There has been growth in the adoption of these technologies by businesses over the past few years."

### 4.6 Anti-patterns - What Makes Content Invisible

#### 1. **The Wall of Text**
```
❌ Single 500-word paragraph with no breaks
```
- Attention mechanisms struggle to identify key points
- High computational cost to extract information

#### 2. **Buried Lead Syndrome**
```
❌ "In this article, we will explore... First, let's consider 
the history... Moving on to background... Finally, the answer is X"
```
- Key information at end = likely missed in synthesis

#### 3. **Ambiguous References**
```
❌ "This solution is 50% better than that one"
```
- Requires context resolution = computational overhead

#### 4. **Over-optimization for Keywords**
```
❌ "Best CRM best CRM software best CRM tools best CRM 2025"
```
- Triggers spam detection in fine-tuned models
- Reduces confidence scores

#### 5. **Conflicting Information**
```
❌ "Prices start at $10 (Actually $25 after trial)"
```
- Confusion = lower confidence = less likely to synthesize

### 4.7 Model-Specific Visibility 

#### For ChatGPT/OpenAI Models

**Leverage Lists**:
```markdown
## Top 5 Features
1. **Feature Name**: Specific benefit
2. **Feature Name**: Specific benefit
```

**Quick Win Sections**:
```markdown
### Quick Start (2 minutes)
- Step 1: Do this
- Step 2: Then this
- Result: Get that
```

**Comparison Tables**:
```markdown
| Feature | Option A | Option B |
|---------|----------|----------|
| Price   | $10/mo   | $20/mo   |
| Users   | Unlimited| 5 users  |
```

#### For Claude/Anthropic Models

**Reasoning Chains**:
```markdown
Because [evidence], we can conclude [insight].
This matters because [implication].
```

**Nuanced Perspectives**:
```markdown
While X is generally true, it's important to note Y.
The evidence suggests Z, though more research is needed.
```

**Structured Arguments**:
```markdown
## Claim
## Supporting Evidence
- Study 1: [Finding]
- Study 2: [Finding]
## Implications
```

#### For Gemini/Google Models

**Authority Signals**:
```markdown
*Last updated: [Date]*
*Reviewed by: [Expert Name, Credentials]*
*Published in: [Reputable Source]*
```

**Factual Precision**:
```markdown
- Launched: January 15, 2025
- Users: 1.2 million (source: Company Report Q1 2025)
- Growth rate: 47% YoY
```

**External Validation**:
```markdown
As reported by [TechCrunch](link), [Reuters](link), 
and [Forbes](link)...
```

### 4.8 Generative Engine Optimization (Checklist)

#### Pre-publish Checklist:

**Structure** ✓
- [ ] Clear H2/H3 hierarchy
- [ ] Bullet points for key info
- [ ] Tables for comparisons
- [ ] Bold for emphasis

**Semantic Density** ✓
- [ ] Key info in first 100 words
- [ ] One idea per paragraph
- [ ] Specific numbers/data
- [ ] No filler words

**Citation Readiness** ✓
- [ ] Self-contained sentences
- [ ] Unique insights/data
- [ ] Clear attributions
- [ ] Recent timestamps

**Model Optimization** ✓
- [ ] Lists for ChatGPT
- [ ] Reasoning for Claude
- [ ] Authority for Gemini
- [ ] Clean extraction for all

### 4.9 Advanced Patterns

#### The "Inverse Pyramid" for AI
Traditional journalism: Most important → least important
AI optimization: Most important → Supporting details → Most important (repeated)

**Why? LLMs may start extraction anywhere in your content.**

#### The "Semantic Triple" Pattern
Group related concepts in threes for better attention clustering:
```
"Fast (100ms), Secure (AES-256), Scalable (10M users)"
```

#### The "Question-Answer Pair" Pattern
```markdown
**Q: What makes X different?**
A: X uses proprietary Y technology, reducing Z by 50%.
```
Highly extractable, matches conversational training data.

### 4.10 Measuring Visibility Success

#### Metrics to Track:

1. **Appearance Rate**: How often your content appears in AI responses
2. **Synthesis Depth**: How much of your content is used
3. **Citation Position**: Where in the response you appear
4. **Sentiment Preservation**: How accurately your message is conveyed

#### Testing Protocol:

1. Query variations on same topic
2. Test across different models
3. Compare against competitor content
4. Track changes over time

FRAMEWORK: [geo content performance tracking framework](https://github.com/KK92-ai/llm-model-behavior-research/blob/main/research/geo-content-performance-tracking-framework.md)

### 4.11 Practical Implementation Guide

#### For New Content:
1. Start with user intent
2. Choose appropriate format (list vs narrative)
3. Optimize for semantic density
4. Add model-specific elements
5. Test with target queries

#### For Existing Content:
1. Audit against visibility stack
2. Identify efficiency bottlenecks
3. Restructure for extraction
4. Add semantic density
5. A/B test changes

### 4.12 The Future of Content Discovery

As models evolve:

- **Multimodal content** will gain importance
- **Real-time signals** will affect visibility
- **User interaction data** may influence synthesis
- **Semantic relationships** will matter more than keywords

Starting now, create content that has the following:

- Building clear information architecture
- Creating unique, valuable insights
- Establishing topical authority
- Maintaining content freshness

## 5. User Behaviour

*Note: This section combines verified research data (clearly cited) with illustrative examples and observed patterns from public discussions. Where specific statistics are provided without citation, they should be understood as examples to illustrate concepts rather than verified data points.*

### 5.1 The Reality of AI User Behavior 

#### The Query Length Reality

**Research Finding**: 

According to Semrush's analysis of 80 million ChatGPT clickstream records (February 2025):
- **Without search enabled**: Average prompt length of 23 words (some reaching 2,717 words)
- **With search enabled**: Average prompt length drops to just 4.2 words (max 301 words)
- **Usage split**: 54% of queries handled without search, 46% with search enabled

Users dramatically change their behavior based on perceived functionality - treating ChatGPT with search like Google (short keywords) but engaging more deeply when search is off.

#### The Intent Revolution

**Key Discovery from the Semrush Study**:
- Only 30% of ChatGPT queries match traditional search intent categories (informational, navigational, transactional, commercial)
- 70% represent entirely new types of intent - problem-solving, brainstorming, exploratory inquiries
- This suggests users are discovering new ways to interact with information that don't fit traditional search paradigms

#### Illustrative Example

While specific satisfaction rates aren't publicly available, the pattern is clear from research and user reports:

**Hypothetical Distribution to Illustrate the Concept**:
```
Short queries (1-5 words):     Lower satisfaction
Medium queries (6-10 words):   Moderate satisfaction  
Detailed queries (11-20 words): Higher satisfaction
Complex queries (21+ words):    Highest satisfaction
```

**The Pattern**: More context = better AI understanding = higher user satisfaction

**Top Query Types (Based on Public Discussions & Research)**:
1. **Google-style**: Short keywords like "best CRM software"
2. **Question-style**: Natural questions like "what is the best CRM software?"
3. **Conversational**: Context-rich like "I need help finding CRM software for my small business"
4. **Detailed**: Full context like "I run a 10-person SaaS startup and need CRM software that integrates with Slack..."

### 5.2 The Query Evolution Curve

Users typically progress through 4 stages:

#### Stage 1: Google Refugees (Weeks 1-2)
```
User: "python tutorial"
AI: *Gives generic response*
User: 😐 "This is just like Google but slower"
```
**Optimization**: Must work for simple queries to capture new users

#### Stage 2: The Awakening (Weeks 3-4)
```
User: "explain python loops with examples"
AI: *Provides detailed explanation*
User: 😊 "Oh, it can do more!"
```
**Optimization**: Educational content that shows AI capabilities

#### Stage 3: Conversation Discovery (Months 2-3)
```
User: "I'm stuck on this Python error, here's my code..."
AI: *Analyzes specific situation*
User: 🤩 "It's like having a tutor!"
```
**Optimization**: Problem-solving content, troubleshooting guides

#### Stage 4: AI Native (Months 3+)
```
User: "Acting as a senior Python developer, review my code for 
production readiness, focusing on performance and security..."
AI: *Provides expert analysis*
User: 🚀 "This is my secret weapon"
```
**Optimization**: Expert-level, nuanced content

### 5.3 The Intent-Expression Gap

#### What Users Want vs. What They Ask

**The Core Problem**: Users often struggle to articulate what they actually need.

**Classic Example**:
- **User Types**: "marketing tips"
- **User Actually Wants**: "How do I get more customers for my local bakery with a $500 monthly budget"
- **Gap**: 95% context missing

#### The Gap Creates Opportunity

**For GEO**: Content that bridges this gap wins. 

Examples:
- "Marketing tips" → "Marketing tips for small businesses"
- "CRM software" → "CRM software for startups under 50 employees"
- "AI tools" → "AI tools for non-technical marketers"

### 5.4 Platform-Specific User Behaviors

*Note: The following behavioral patterns are based on public discussions, user reports, and observable trends rather than specific statistical studies.*

#### ChatGPT Users
**Primary Use Cases**:
1. Quick answers (38%)
2. Content creation (27%)
3. Code help (19%)
4. Learning/tutoring (16%)

**Behavioral Traits**:
- Expect immediate responses
- Prefer lists and structures
- High retry rate (3.2 attempts average)
- Trust degrades after conflicting answers

**Query Evolution**:
```
Day 1: "write email"
Day 30: "write a professional email declining a meeting"
Day 90: "as a diplomatic communications expert, help me write..."
```

#### Claude Users
**Primary Use Cases**:
1. Research/analysis (41%)
2. Writing assistance (29%)
3. Complex reasoning (22%)
4. Ethical discussions (8%)

**Behavioral Traits**:
- Longer initial queries (17 words avg vs 12 for ChatGPT)
- More follow-up questions
- Higher tolerance for nuanced responses
- Appreciate uncertainty acknowledgment

**Query Evolution**:
```
Day 1: "analyze this data"
Day 30: "what patterns do you see in this data"
Day 90: "help me understand the implications of these patterns for our Q2 strategy"
```

#### Gemini Users
**Primary Use Cases**:
1. Fact-checking (44%)
2. Current events (31%)
3. Local information (15%)
4. Academic research (10%)

**Behavioral Traits**:
- Highest use of "latest" and year markers
- More likely to ask follow-up verification
- Prefer cited sources
- Lower creative task usage

### 5.5 Prompting Patterns That Drive Engagement

#### The Trust Builders

**1. The Expertise Frame**
```
Bad: "marketing advice"
Good: "as a marketing expert, what would you recommend for..."
Better: "acting as a CMO with startup experience, how would you..."
```
*Why it works*: Activates specialized knowledge patterns

**2. The Context Sandwich**
```
[Context] I run a 10-person B2B SaaS startup
[Question] What CRM should we use?
[Constraints] Budget is $500/month, needs mobile app
```
*Why it works*: Matches training data conversation patterns

**3. The Progressive Disclosure**
```
Query 1: "I need help with marketing"
Response: *AI asks clarifying questions*
Query 2: "It's for my bakery, I have $500/month"
Response: *More targeted advice*
```
*Why it works*: Builds context naturally, higher engagement

#### Patterns That Kill Engagement

**1. The Keyword Stuffer**
```
"best CRM software 2025 top rated cheap affordable small business"
```
*Result*: AI treats as spam, generic response

**2. The Assumption Trap**
```
"fix this: [no context about what 'this' is]"
```
*Result*: AI has to guess, often wrong

**3. The Essay Request**
```
"write me a 5000 word article about everything related to CRM"
```
*Result*: Generic, unfocused content

### 5.6 User Behavior Insights for GEO

#### The Discovery Patterns

**How users find new tools/products via AI**:
1. **Problem-first** (47%): "I need to track customer emails better"
2. **Comparison** (31%): "Salesforce vs HubSpot for small business"
3. **Category exploration** (22%): "what types of CRM software exist"

**GEO Implication**: Optimize for problem-first discovery, not just category terms

#### Trust Signals Users Seek

**What makes users trust AI recommendations**:
1. Specific details (pricing, features)
2. Pros AND cons mentioned
3. Use case matching
4. Recent information
5. Alternatives provided

**GEO Optimization**: Include all trust signals in your content

### 5.7 The Search-Enabled vs Pure AI Divide

#### Based on Semrush's 80M Record Analysis:

**Search Disabled (54% of queries)**:
- Longer, detailed prompts (avg 23 words)
- More exploratory, creative tasks
- Problem-solving focus
- Up to 2,717 word prompts observed

**Search Enabled (46% of queries)**:
- Short queries (avg 4.2 words)
- Google-like behavior
- Fact-checking focus
- Maximum 301 word prompts

**GEO Implication**: Same users, completely different behavior patterns. Optimize for both modes.

### 5.8 Mobile Usage Patterns

*Note: While specific mobile vs desktop statistics for ChatGPT aren't publicly available, general patterns can be observed:*

**Mobile Behavior Indicators**:
- Shorter queries due to typing constraints
- More voice-to-text usage
- Quick task focus
- Single-session interactions

**Desktop Behavior Indicators**:
- Longer, more complex queries
- Copy-paste heavy usage
- Research-oriented sessions
- Multi-tab workflows

**Optimization Strategy**: Create content that works for both quick mobile lookups and deep desktop research.

### 5.9 Query Intent Categories & GEO Strategies

#### 1. Informational (41%)
**User**: "how does CRM software work"
**GEO Strategy**: Educational content, fundamentals, "what is" content

#### 2. Navigational (19%)
**User**: "Salesforce pricing"
**GEO Strategy**: Brand-specific content, comparison pages

#### 3. Transactional (23%)
**User**: "sign up for CRM free trial"
**GEO Strategy**: Clear CTAs, feature highlights, social proof

#### 4. Investigational (17%)
**User**: "which CRM is best for real estate agents"
**GEO Strategy**: Niche-specific content, use case optimization

### 5.10 The Prompt Engineering Revolution

#### Evolution of The User:
- users now save "prompt templates"
- use browser extensions for better prompts
- have taken prompt engineering courses

#### Emerging Patterns:

**The Framework Users**:
```
"Using the STAR method, analyze..."
"Apply the 80/20 principle to..."
"Through the lens of [framework]..."
```

**The Role Players**:
```
"You are a [specific expert role]..."
"Pretend you're my [relationship]..."
"Channel the expertise of [famous person]..."
```

**The Constraint Setters**:
```
"In exactly 3 bullet points..."
"Using only simple words a 5th grader would understand..."
"Without using any jargon..."
```

### 5.11 Platform Migration Patterns

**Users typically**:
1. Start with ChatGPT (73%)
2. Try Claude for "thinking" tasks (34% migrate)
3. Use Gemini for facts/current events (28% migrate)
4. Develop multi-tool workflows (19% use all three)

**GEO Implication**: Same content needs different optimization per platform based on user intent migration

### 5.12 The Psychology of AI Interaction

#### Trust Building Progression:
```
Query 1-5: Testing boundaries
Query 6-20: Finding sweet spots
Query 21-50: Developing patterns
Query 50+: Habitual usage
```

#### Abandonment Triggers:
1. Hallucination discovered (42% stop trusting)
2. Outdated information (38% leave)
3. Generic responses (31% disengage)
4. Over-cautious disclaimers (27% frustrated)

**GEO Protection**: Ensure content is accurate, specific, and actionable

### 5.13 Future Behavior Predictions

**Observable Shifts**:
- Prompt engineering becoming mainstream (15% already use templates)
- Growing adoption of AI-specific browser extensions
- Increasing investment in prompt engineering education
- Early stages of multi-modal output like image catalogues for shopping etc.

**Reasonable Predictions for 2026**:
- Average query length likely to increase as users become more sophisticated
- Multi-turn conversations becoming standard practice
- Voice queries growing in prevalence, multi modal output for many query types
- AI-native generation defaulting to AI for information needs

**Preparation Strategies**:
- Create conversation-friendly content
- Optimize for voice search patterns
- Build prompt-friendly resources
- Develop AI-first content strategies

### 5.14 Practical GEO Tactics for Real User Behavior

#### 1. The Query Expansion Strategy
**Optimize for**:
- Short query: "CRM software"
- + Context: "CRM software for small business"
- + Intent: "affordable CRM software for small business"
- + Constraint: "CRM software under $50 for small business"

#### 2. The Problem Interception
Instead of: "Our CRM is the best"
Try: "If you're struggling to keep track of customer emails..."

#### 3. The Comparison Trap
Users love comparisons but hate choosing. Provide:
- Clear winner for specific use cases
- "If X, choose Y" frameworks
- Decision trees

#### 4. The Fresh Signal
Users increasingly add years to queries:
- Maintain year-stamped content
- Update timestamps visibly
- Include "last updated" prominently

### 5.15 Verified Findings

1. **Query length varies dramatically by mode** - 23 words without search vs 4.2 words with search (Semrush)
2. **New intent types emerging** - 70% of ChatGPT queries don't match traditional search patterns
3. **Massive adoption** - 800M weekly active users, 1B+ daily queries
4. **Young users lead adoption** - 43% of 18-29 year olds have used ChatGPT vs 6% of 65+
5. **Enterprise adoption is widespread** - 92% of Fortune 500 companies use it

### 5.16 Test Content Creation 
(for both short and detailed query type)

**Immediate**:
1. Audit content for both short (4-word) and detailed (20+ word) query optimization
2. Create problem-first discovery paths
3. Add trust signals to all content
4. Develop quick-answer formats for search-enabled mode

**Next Quarter**:
1. Build conversation-friendly resources
2. Create use-case specific content
3. Develop prompt templates for your industry
4. Test multi-turn content strategies

**Long-term**:
1. Prepare for voice search growth
2. Build AI-native content experiences
3. Develop expertise positioning
4. Monitor emerging usage patterns

### 5.17 Research Sources & References

**Primary Research Data**:
- Semrush (2025): "Investigating ChatGPT Search: Insights from 80 Million Clickstream Records"
- OpenAI public statements on user numbers (800M weekly active users, 1B daily queries)
- Various 2024-2025 studies on ChatGPT demographics from Backlinko, AIPRM, NerdyNav, Keywords Everywhere

**Note on Data Usage**: Where specific percentages or distributions are provided without direct citation, these should be understood as illustrative examples to demonstrate concepts rather than verified statistics. The field of AI user behavior research is rapidly evolving, and comprehensive academic studies are still emerging.


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
22. **Visibility is multi-layered** - Must succeed at every level from crawling to synthesis
23. **Computational efficiency matters** - LLMs prefer content that's easy to process
24. **Semantic density beats word count** - Pack more information into fewer tokens
25. **Structure determines synthesis** - How you organize information affects if it's used
26. **Model-specific optimization works** - Different tactics for different model families
27. **Intent alignment is crucial** - Match content format to query type
28. **Anti-patterns can kill visibility** - Avoid walls of text, buried leads, ambiguity
29. **Users underutilize AI capabilities** - Most start with Google-style queries
30. **Platform behaviors differ** - ChatGPT for quick tasks, Claude for deep thinking
31. **Trust builds progressively** - Through consistent, accurate responses
32. **Context improves satisfaction** - More detailed prompts generally yield better results
33. **Prompt engineering is emerging** - 15% already use templates, courses proliferating



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
