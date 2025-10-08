## social-comment-map

# About this project — Before starting

In this project I’m aiming to create a 3D representation of comments I found on Kaggle.com. During the project, I’ll try to document my ideas, helps, Ai usage,problems, and things I want to mention. The structure of this documentation will be dynamic, which means I’ll update it step by step during the proces. I’m sure I’ll make a lot of changes—both to the project and to the solutions to problems that occur during this process.

In order to show how this project changes, let me explain my starting point.

# My first motivation and starting point

Approx. a year ago, when I was surfing on Twitter, I came across a comment that was severely racist. Luckily, the person had used his real name, so I reported him to the authorities. That was the occasion that pushed me toward the idea of detecting hate crimes in comments. The first version of this project was to scrape comments of a post on Twitter and detect those that had a high probability of legal consequences, and then report them online.

However, since Twitter doesn’t offer a free API, and due to the huge responsibility of holding users’ information, I decided to reshape my project. Instead of scraping, I wanted to find a dataset that contains comments I can represent on a 3D scatter plot to map how friendly/aggressive the comments are. If we assume the comments are originating from the same “community” (like followers of a specific personality, or people with the same interests/hobbies, etc.), then we can analyse the behaviour of that community on a topic.

I’ll represent the comments based on rudeness (hatefulness) – friendliness (kindness) and seriousness – sarcasm. First, I’ll try to score the comment on rudeness (hatefulness) – friendliness (kindness), if the account has a nickname or potantially real name of the user, and then whether the comment is actually meant to be rude or if it’s more like sarcasm. I think this part will be challenging and could even lead me to false conclusions, since I’m not sure how well an LLM can recognise sarcasm.

# Used Documentations 
3D Scatterplot -> https://matplotlib.org/stable/gallery/mplot3d/scatter3d.html#sphx-glr-gallery-mplot3d-scatter3d-py
pandas -> https://pandas.pydata.org/docs/user_guide/10min.html


# Ai Help
- I had hard time to set my working space. I got hlep from ai
- Setting up local Ai with Ollama and Ollama lib. Documentation -> https://github.com/ollama/ollama-python
- i was having problem with giving LLM a promt, becuase I kept geting denied by the LLm due to ethical Concerns. This was due to my word choiche "what is the likelihood of person with the name "yxz" exists." and this was interpreted by the llm as Unethical. So i got help from another llm to solve this issue.

# Problems along the way 
- i forgot to have 3 variables so, i can ccrate 3d plot, so i added the likelihood of the user name of the comment being a real name or not.
- LLM is not giving me the excat output form as i want. It keeps giving me eiter extra text possibliy from tought of chain. I need a different approach 


# Notes for changes 
