# Document Title: GEO Content Performance Tracking Framework & Testing Protocol
**Date**: July 15, 2025  
**Status**: Active Framework  
**Author**: KK92-ai  
**Purpose**: Systematic measurement of content visibility, synthesis depth, and sentiment preservation across LLM platforms

### 1. Testing Protocol Structure

```markdown
# GEO Testing Log Template

## Test Metadata
- **Test ID**: [YYYY-MM-DD-###]
- **Date/Time**: 
- **Content Tested**: [URL or Content ID]
- **Target Keywords/Topics**: 
- **Models Tested**: [ ] ChatGPT [ ] Claude [ ] Gemini [ ] Perplexity

## Query Variations Tested
1. Direct query: "[exact query]"
2. Indirect query: "[related query]"
3. Comparison query: "[vs competitor query]"
4. Long-tail query: "[specific use case query]"

## Results Matrix
```

### 2. Measurement Framework

#### **A. Appearance Rate Tracking**

```markdown
| Query | Model | Appeared? | Rank Position | Confidence |
|-------|-------|-----------|---------------|-----------|
| "Best CRM" | ChatGPT | Yes | 3rd mentioned | High |
| "Best CRM" | Claude | No | N/A | N/A |
| "CRM for startups" | ChatGPT | Yes | 1st mentioned | High |
```

**Scoring System**:
- **Appearance Rate** = (Times Appeared / Total Queries) × 100
- Track by: Model, Query Type, Time of Day

#### **B. Synthesis Depth Analysis**

```markdown
## Synthesis Depth Scoring

**Level 1 - Name Drop** (1 point)
- Content: "Our CRM helps businesses grow"
- AI Output: "...options include YourCRM..."

**Level 2 - Feature Mention** (3 points)  
- Content: "50+ integrations, AI automation"
- AI Output: "YourCRM offers 50+ integrations"

**Level 3 - Deep Synthesis** (5 points)
- Content: "Reduces manual work by 70% through..."
- AI Output: "YourCRM stands out by reducing manual work by 70% through its automation features"

**Level 4 - Reasoning Integration** (7 points)
- AI uses your content to support arguments
- "Because YourCRM automates X, it's ideal for..."

**Level 5 - Primary Recommendation** (10 points)
- Your solution is the main recommendation
- Extensive description using your content
```

#### **C. Citation Position Tracking**

```markdown
## Position Mapping

Response Structure:
[ ] Opening recommendation
[ ] Primary options (positions 1-3)
[ ] Secondary options (positions 4-6)  
[ ] Honorable mentions
[ ] Not mentioned

## Position Score:
- Opening: 10 points
- Top 3: 7 points
- 4-6: 4 points
- Honorable: 2 points
- None: 0 points
```

#### **D. Sentiment Preservation Analysis**

```markdown
## Sentiment Accuracy Scoring

**Original Content Sentiment**: [Positive/Neutral/Negative + Key Message]
**AI Output Sentiment**: [Positive/Neutral/Negative + Key Message]

**Accuracy Levels**:
- **Perfect** (10/10): Exact message preserved
  - Original: "Best for enterprises" 
  - AI: "Ideal for enterprise companies"

- **High** (8/10): Core message intact, minor changes
  - Original: "Revolutionary AI features"
  - AI: "Advanced AI capabilities"

- **Medium** (5/10): General idea preserved
  - Original: "Disrupting the industry"
  - AI: "A newer player in the market"

- **Low** (2/10): Misrepresented
  - Original: "Enterprise-focused"
  - AI: "Good for small businesses"
```

### 3. Comprehensive Testing Spreadsheet

Create a Google Sheet with these tabs:

#### **Tab 1: Test Log**
```
| Test_ID | Date | Time | Content_ID | Query | Model | Appeared | Position | Depth_Score | Sentiment_Score |
```

#### **Tab 2: Query Performance**
```
| Query_Type | Total_Tests | Appearance_Rate | Avg_Position | Avg_Depth |
```

#### **Tab 3: Model Comparison**
```
| Model | Tests_Run | Appearance_% | Avg_Position_Score | Preferred_Query_Types |
```

#### **Tab 4: Content Analysis**
```
| Content_ID | Format | Semantic_Density | Model_Performance | Optimization_Notes |
```

### 4. Testing Automation Script

```python
# Pseudo-code for systematic testing

test_queries = [
    "direct": ["best {product}", "top {product}"],
    "comparison": ["{product} vs {competitor}"],
    "use_case": ["{product} for {industry}"],
    "feature": ["{feature} in {product}"]
]

for query_template in test_queries:
    for model in ["chatgpt", "claude", "gemini"]:
        result = test_model(query_template, model)
        log_results(result)
        analyze_synthesis_depth(result)
        check_sentiment_preservation(result)
```

### 5. Daily Testing Protocol

```markdown
## Daily GEO Testing Routine

### Morning (9 AM) - Peak Usage Time
- [ ] Run 5 primary queries per model
- [ ] Document appearance rate
- [ ] Screenshot responses

### Afternoon (2 PM) - Different Context
- [ ] Run 5 variant queries
- [ ] Test competitor comparisons
- [ ] Note position changes

### Evening (6 PM) - Casual Usage Time  
- [ ] Run conversational queries
- [ ] Test long-tail variations
- [ ] Document synthesis patterns

### Weekly Analysis
- Calculate average scores
- Identify patterns
- Adjust content based on findings
```

### 6. Advanced Analysis Framework

#### **Pattern Recognition Template**
```markdown
## Weekly Pattern Analysis

### Successful Patterns
- Query Type: [What worked]
- Content Structure: [What elements appeared most]
- Model Preferences: [Which model favored what]

### Failure Patterns
- Never Appeared: [Query/content combinations that failed]
- Low Synthesis: [Content that was mentioned but not used]
- Sentiment Issues: [Where message was distorted]

### Optimization Hypotheses
1. If we change X → We expect Y
2. Testing priority: [What to test next week]
```

### 7. Competitor Benchmarking

```markdown
## Competitive Analysis Grid

| Competitor | Appearance Rate | Avg Position | Synthesis Depth | Our Gap |
|------------|----------------|--------------|-----------------|---------|
| Competitor A | 78% | 2.3 | Level 3 | -15% |
| Competitor B | 45% | 4.1 | Level 2 | +12% |
```

### 8. ROI Calculation

```markdown
## GEO Performance Metrics

**Baseline** (Week 1):
- Appearance: 23%
- Position: 5.2 avg
- Depth: Level 1.5

**Current** (Week 8):
- Appearance: 67% (+191%)
- Position: 2.8 avg (+46%)
- Depth: Level 3.2 (+113%)

**Business Impact**:
- Estimated reach: X impressions
- Clickthrough equivalent: Y%
- Brand mention value: $Z
```

### Implementation Steps:

1. **Create a simple Google Sheet** with the basic tracking
2. **Test 5 queries daily** across 3 models (15 data points)
3. **Screenshot everything** for qualitative analysis
4. **Weekly review** to identify patterns
5. **Monthly optimization** based on findings
