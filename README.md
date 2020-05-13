## Language Models to study cognitive language understanding


### Use Model-Model communication

```
python interactive.py -t blended_skill_talk -mf zoo:blender/blender_90M/model
```

### Use pretrained ParlAI

```
git clone https://github.com/facebookresearch/ParlAI.git ~/ParlAI
cd ~/ParlAI; python setup.py develop
python projects/wizard_of_wikipedia/scripts/interactive_retrieval_model.py
```


### What is this?

- What is the elevator pitch of your idea?
    - We want to study learning in an individual from observing two person communication.
    - Eg, Bob, an expert in linguistics is having a conversation with Alice, a virologist. Now, Ted, unknown to both linguistics and virology is observing the conversation. 
    - What aspects will Ted learn from this conversation?
    - We plan is to use both a machine learning model as Ted and an actual human as Ted in this research.
    - The goal of the research would be to evaluate what aspects of language Ted learns from the conversation.

- What steps will you follow to complete the project?
    - We'll train two language models with different domain knowledge, representing Bob and Alice. 
    - Bob and Alice will have a 2-agent conversation on a topic. We'll save this transcript, say as $$T$$.
    - We would also prepare a shuffled version of the transcript $$T^\prime$$. This would help us understand the kind of knowledge and language acquired by Ted.
    - We'll train another language model, say Ted, using $$T$$.
    - To evaluate the learning of Ted, we would evaluate an information theoretic measure called **perplexity**.  [Perplexity](https://thegradient.pub/understanding-evaluation-metrics-for-language-models/) is the measure of entropy in predicting the following symbol.
    - We would evaluate the perplexity of Ted on both $$T$$ and $$T^\prime$$. 
    - Finally, we would present $$T$$ to a human and evaluate what kind of knowledge is grasped by a human.

- What toolkits can you draw from or how much will you have to implement yourself?
    - [ParlAI](https://github.com/facebookresearch/ParlAI)
    - ParlAI has support for multi-agent communication and training of language models.
    - We would use language models from the framework to simulate Bob and Alice.

- What data sources will you consult?
    - [Wizard of Wikipedia](https://parl.ai/docs/zoo.html#wizard-of-wikipedia-models)

- What papers have you identified that might form background literature?
    - Dinan, Emily et al. “Wizard of Wikipedia: Knowledge-Powered Conversational agents.” __ArXiv__ abs/1811.01241
    - Flavell, John H.. “Development of children's knowledge about the mental world.” (2000).
    - Zimmerman, Frederick J. et al. “Teaching by listening: the importance of adult-child conversations to language development.” __Pediatrics__ 124 1 (2009)

- Is there some idea you can build upon from the background literature given the time allotted for this class?
    - The language acquisition in babies is based on the conversation they hear between their parents.
    - Now, if provided with two different kind of conversation; one with the original sentence order intact, another with words in shuffled order.
    - Babies listening to the shuffled order of conversation, are highly perplexed and tries to pay attention to the speaker. 



