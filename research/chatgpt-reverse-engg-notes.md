# ChatGPT Ranking Algorithm 

## Executive Summary

This analysis examines claims about ChatGPT's internal ranking algorithm based on reverse-engineered source code written by an SEO expert [Metehan](https://open.substack.com/pub/metehanai/p/how-i-reverse-engineered-chatgpts?r=7kzh&utm_campaign=post&utm_medium=web&showWelcomeOnShare=false)

---

## Neural Reranker Analysis: "ret-rr-skysight-v3"

### **Claimed Configuration**
```javascript
reranker_model: "ret-rr-skysight-v3"
```
### Notes and learnings

Reranking as standard practice in LLMs

- ChatGPT allegedly uses a neural network to reorder initial search results
- Results aren't just retrieved—they're intelligently reranked
- Getting into initial results ≠ final ranking position

**Content must survive reranking, not just initial retrieval**
- Optimize for semantic relevance, not just keyword matching
- Focus on comprehensive, authoritative content
- Ensure content quality exceeds competitors in your topic space

---

## Freshness 

### **Claimed Configuration**
```javascript
use_freshness_scoring_profile: true
```

### Notes and learnings
- ChatGPT allegedly prioritizes recent content through dedicated scoring
- Prompt instruction "Use the web tool for recent events / fresh information"
- Recent mediocre content > older comprehensive content (actually this is query-dependent so read break down below)

**Freshness Wins For:**

- Breaking news and current events
- Trending topics and viral content
- Product releases and new technologies
- Seasonal/recurring events
- Regulatory changes and updates

**Quality/Comprehensiveness Wins For:**

- How-to guides and tutorials
- Foundational concepts and definitions
- Research and case studies
- Technical documentation
- Evergreen educational content

### Mental Model

Time-sensitive content → Update frequently (monthly/quarterly)
Evergreen content → Update strategically (annually or when outdated)


### Content Creation Cycle

1. **Quarterly Content Updates**
   - Minimum refresh cycle: 90 days for competitive topics
   - Add new sections rather than just editing existing ones
   - Include recent industry developments and data

2. **Freshness Signals**
   - Use current year in titles and meta descriptions
   - Reference recent events and developments
   - Include "updated" or "2025" in strategic locations

---

## Multi-Stage Filtering Pipeline

### **Claimed Configuration**
```javascript
enable_query_intent: true
enable_source_filtering: true
enable_mimetype_filtering: true
vocabulary_search_enabled: true
use_coarse_grained_filters_for_vocabulary_search: false
```

### **Stage-by-Stage Breakdown**

#### **Stage 1: Intent Detection**
- Determines query type (definition, comparison, tutorial, etc.)
- Content structure must match search intent clearly

#### **Stage 2: Vocabulary Analysis**
- Recognizes domain-specific terminology
- Proper technical vocabulary becomes ranking factor

#### **Stage 3: Source Filtering**
- Different treatment for different source types
- Source authority and type influence ranking

#### **Stage 4: MIME Type Awareness**
- Recognizes HTML, PDF, video content differently
- Content format affects discoverability

#### **Stage 5: Fine-Grained Filtering**
- Precise evaluation vs. broad categorization
- Granular optimization matters more than general tactics

### Learning

#### **Intent Clarity Optimization**
```markdown
❌ Poor: "Guide to Marketing Tools"
✅ Good: "Complete Comparison: 15 Marketing Automation Tools (2025 Buyer's Guide)"
```

#### **Technical Vocabulary Integration**
1. **Research Domain Language**
   - Use industry-specific terminology naturally
   - Include technical definitions and explanations
   - Don't sacrifice readability for keyword density

2. **Authority Signal Development**
   - Demonstrate expertise through precise language
   - Reference industry standards and frameworks
   - Use acronyms and technical terms appropriately

---

## "Slurm"

### **Claimed Configuration**
```javascript
use_light_weight_scoring_for_slurm_tenants: true

// Connected services:
"slurm_dropbox"
"slurm_sharepoint" 
"slurm_box"
"slurm_canva"
"slurm_notion"
```

###  **What is Slurm?**
- Third-party connected services (Dropbox, Notion, etc.)
- Lightweight scoring for private content vs. full neural reranking for public web
- Public web content faces more sophisticated evaluation


#### **Intent Clarity Optimization**
1. **Content Structure Alignment**
   ```markdown
   For "How to" queries → Step-by-step guides
   For "Best" queries → Comparison with clear winner
   For "What is" queries → Definition + comprehensive explanation
   ```

2. **Technical Vocabulary Mastery**
   - Research industry-specific terminology
   - Include glossaries and technical definitions
   - Use precise language without sacrificing readability

### **Experimental Strategies**

#### **Reranking Optimization**
1. **Comprehensive Topic Coverage**
   - Create topic clusters rather than standalone articles
   - Cover related subtopics within main content
   - Cross-link related concepts internally

2. **Multi-Format Content**
   - Include text, images, and structured data
   - Create downloadable resources (PDFs, guides)
   - Develop interactive elements where appropriate

### **Advanced Monitoring & Testing**

#### **AI Visibility Tracking**
1. **Monitor AI Citations**
   - Track mentions in ChatGPT responses
   - Monitor competitor citations
   - Document ranking patterns over time

2. **Content Performance Analysis**
   - A/B test freshness signals
   - Measure impact of technical vocabulary
   - Track intent clarity improvements
---

## Future Research Priorities

### **Knowledge Gaps to Address**
1. **Exact Reranking Mechanisms**: How does neural reranking actually work?
2. **Freshness Scoring Details**: What specific signals determine freshness?
3. **Intent Classification**: How are different query intents detected and weighted?

---

## Final Recommendations

### **Implement Immediately**
1. **Content Freshness Strategy**: Update old content, monitor trends
2. **Intent Clarity**: Ensure content purpose is immediately clear
3. **Technical Vocabulary**: Use industry-appropriate terminology

### **Test Carefully**
1. **Reranking Optimization**: Comprehensive topic coverage strategies
2. **Multi-format Approaches**: Diversify content types and formats
3. **Advanced Freshness Signals**: Year references, recent examples

### **Monitor & Research**
1. **AI Citation Tracking**: Document what gets cited and why
2. **Competitive Intelligence**: How are leaders in your space optimizing?
3. **Algorithm Changes**: Stay alert for updates to ranking factors

**Remember**: While these insights provide valuable direction, the fundamental principle remains unchanged—create genuinely valuable, authoritative, and current content that serves user needs better than alternatives.

Research source and credits go to this Substack note by [Metehan](https://open.substack.com/pub/metehanai/p/how-i-reverse-engineered-chatgpts?r=7kzh&utm_campaign=post&utm_medium=web&showWelcomeOnShare=false)
