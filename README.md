# social-comment-map

# About this project — Before starting

In this project, I’m aiming to create a 3D representation of comments I found on Kaggle.com. During the project, I’ll document my ideas, AI usage, problems, and things I want to mention. The structure of this documentation will be dynamic, meaning I’ll update it step by step throughout the process. I’m sure I’ll make many changes—both to the project and to the solutions for the problems that occur along the way.
To show how this project evolves, let me explain my starting point.

# My first motivation and starting point

About a year ago, while scrolling through Twitter, I came across a comment that was severely racist. Luckily, the person had used his real name, so I was able to report him to the authorities. That moment pushed me toward the idea of detecting hate crimes in comments.
The first version of this project was meant to scrape comments from a Twitter post, detect those with a high probability of legal consequences, and report them automatically.

However, since Twitter no longer offers a free API, and due to the huge responsibility of handling users’ information, I decided to reshape the project. Instead of scraping, I wanted to find a dataset containing comments that I could represent on a 3D scatter plot to visualize how friendly or aggressive they are.
If we assume the comments originate from the same “community” (for example, followers of a specific personality, or people with shared interests or hobbies), then we can analyze that community’s behavior around a given topic. I’ll represent the comments based on rudeness (hatefulness)  and seriousness(sarcasm).


# Used Documentation

- 3D Scatterplot: [Matplotlib Example](https://matplotlib.org/stable/gallery/mplot3d/scatter3d.html#sphx-glr-gallery-mplot3d-scatter3d-py)
- pandas: [Pandas Guide](https://pandas.pydata.org/docs/user_guide/10min.html)

# AI Help

- I had a hard time setting my working directory — AI helped me solve that.
Setting up a local AI environment with Ollama and its Python library: Ollama Docs
- I had issues designing prompts for the LLM, since I kept getting rejected due to “ethical concerns.” This happened because of my wording (“What is the likelihood that a person with the name ‘xyz’ exists?”), which the model misinterpreted. Another LLM helped me rephrase it.
- I also used AI to understand the 3D plot documentation more effectively.
- Grammer correction of Read Me page. 

# Problems along the way

- I initially forgot that I needed three variables to create a 3D plot, so I added a “nickname likelihood” variable — estimating whether a username looks like a real name.
- The LLM didn’t output results in the exact format I needed. It often returned extra text or reasoning (likely due to DeepSeek’s “chain of thought”). I solved this issue by switching to another model (Lama 8b).
- My current approach using a for loop and sending three separate calls is not optimal. It’s time-consuming and inefficient. A better approach would be to request all three scores in one LLM call, which would reduce processing time.

# About this project — After finishing

I completed the project successfully.
Due to limited processing speed, I was only able to analyze the first 600 comments. That’s not enough to detect the most extreme cases, which is visible in the 3D plot. There’s a clear cluster of comments in one corner that could be considered friendly or harmless, mostly posted by "anonymous" accounts.

I also want to mention some of the challenges I faced.
Because of a short planning phase, I overlooked the need for three separate scores to visualize the comments in 3D. I solved this by adding a nickname_score column, representing the likelihood that a username is a real, legal name.

However, this introduced another problem that the dataset didn’t include usernames. So, I decided to generate random usernames using LLM. Unfortunately, my prompt wasn’t perfect, and the model often returned obviously fake names (which, to be fair, reflects social media reality). As a result, most nickname scores ended up between 0% and 30%.
Another possible reason for the clustering of comments could be that the dataset was already filtered for hate speech or violent content, which limited the range of “toxic” examples
