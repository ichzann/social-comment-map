## social-comment-map

# About this project — Before starting

In this project I’m aiming to create a 3D representation of comments I found on Kaggle.com. During the project, I’ll try to document my ideas, helps, Ai usage,problems, and things I want to mention. The structure of this documentation will be dynamic, which means I’ll update it step by step. I’m sure I’ll make a lot of changes—both to the project and to the solutions to problems that occur during this process.

In order to show how this project changes, let me explain my starting point.

# My first motivation and starting point

Approx. a year ago, when I was surfing on Twitter, I came across a comment that was severely racist. Luckily, the person had used his real name, so I reported him to the authorities. That was the occasion that pushed me toward the idea of detecting hate crimes in comments. The first version of this project was to scrape comments of a post on Twitter and detect those that had a high probability of legal consequences, and then report them online.

However, since Twitter doesn’t offer a free API, and due to the huge responsibility of holding users’ information, I decided to reshape my project. Instead of scraping, I wanted to find a dataset that contains comments I can represent on a 3D scatter plot to map how friendly/aggressive the comments are. If we assume the comments are originating from the same “community” (like followers of a specific personality, or people with the same interests/hobbies, etc.), then we can analyse the behaviour of that community on a topic.

I’ll represent the comments based on rudeness (hatefulness) – friendliness (kindness) and seriousness – sarcasm. First, I’ll try to score the comment on rudeness (hatefulness) – friendliness (kindness), and then whether the comment is actually meant to be rude or if it’s more like sarcasm. I think this part will be challenging and could even lead me to false conclusions, since I’m not sure how well an LLM can recognise sarcasm.
