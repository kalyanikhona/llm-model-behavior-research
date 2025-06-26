# LLM Search Behavior Taxonomy: A Comprehensive Framework
*By Kalyani Khona | Last Updated: June 2025*

## Opening notes

LLMs adoption is challenging beyond the basic search due to its complicated taxonomy, model selection, different platform types etc. This taxonomy categorises distinct search and response patterns observed across major Large Language Models (ChatGPT, Claude, Perplexity, Grok) to help researchers and practitioners understand when and how LLMs access external information.
I will be using references from here into my logbook so for ease of understanding my logbook, please check this guide first.  

## Pure generative (I call this "Gen-Query" in my logbook)

The LLM just answers from memory. No googling, no searching, just information from its training data.
In short, the model respond exclusively from pre-trained knowledge without conducting any external searches.

### When to use this, key characteristics etc

- Since no search is conducted, this is good for historic references that do not need update e.g. capital of France or history of WW2
- Bad for current affair searches because of knowledge cutoff (limitation)
- Immediate answers, quick response, no citations
