prompting engieering -- clear and specific  
   iterative process... 

Prompting is an essential skill for getting the most out of generative AI. To get the best results from an AI tool, you need to craft a good prompt. A good prompt follows a simple framework: Task, Context, References, Evaluate, and Iterate. Explore how you can use this framework to elevate your prompting and unlock more of AI’s benefits.


Specify the task
Specifying your task is the foundation of every prompt. Describe in detail what you want the AI tool to do, be clear and avoid ambiguity. If you write a task with vague instructions, it can result in an output that’s irrelevant or incorrect.  Your task may include a persona and a format preference so that the task is specific: 

Task: What action do you want the tool to help you with? For example, you might ask the tool to write an email or create an image. 

Persona: What expertise do you want the AI tool to draw from, and who is the audience? For example, you might ask the tool to complete the task with the expertise of an IT professional, or ask it to create an output geared towards a specific audience like your manager or team. 

Format: How do you want the output to be formatted? For example, you might ask the AI tool to create a bulleted list or a comparison table.

Here's an example of a prompt that includes a specific task, a persona and a format:

You're a concert promoter specializing in raising ticket sales in the alternative rock music industry. Create a social media post about an upcoming music festival that speaks to the local music community while attracting out-of-state festival-goers. Limit the post to 125-characters. Include 5 relevant hashtags.

Provide necessary context
Including detailed context in your prompts can narrow an AI tool's focus, enabling it to produce more tailored and effective output. Contextual information in your prompts might include:

Reasons and objectives for performing the task

Rules or guidelines that the output must follow

Relevant background information the tool should consider

These details can help an AI tool better understand your needs. Here's an example of a prompt that provides necessary context:

You're a concert promoter specializing in raising ticket sales in the alternative rock music industry. Create a social media post about an upcoming music festival that speaks to the local music community while attracting out-of-state festival-goers. Limit the post to 125-characters. Include 5 relevant hashtags. The local audience is primarily college students and young professionals (age 21-35) who follow indie rock. The festival features 12 bands over 2 days, with camping options and local food vendors.

This prompt will likely generate a more engaging and effective output that's tailored to a specific audience—without requiring additional time spent iterating on the initial prompt.

Include references as examples
References provide examples or resources that illustrate what you want an AI tool to produce. They specify details about your desired output, such as the style, tone, and format. Depending on the AI tool, you can include text, images, audio, or even video as references.

When including references in your prompts, consider these suggestions:

Briefly explain how the references relate to the task.

Use 2-5 high-quality examples that closely align with your needs.

Include your own work or open-source examples if relevant.

Here's an example of a prompt that includes references:

You're a concert promoter specializing in raising ticket sales in the alternative rock music industry. Create a social media post about an upcoming music festival that speaks to the local music community while attracting out-of-state festival-goers. Limit the post to 125-characters. Include 5 relevant hashtags. The local audience is primarily college students and young professionals (age 21-35) who follow indie rock. The festival features 12 bands over 2 days, with camping options and local food vendors. Here are examples of successful posts from similar events:

- Example 1: Where mountains meet music: Indie Rocks Festival returns! Your favorite local bands + national acts. Good eats & Sleep under the stars! #Indie Rocks #SupportLocalMusic

- Example 2: Join Indie Fest under the desert skies! 2 nights of raw sound 2 move you + camping vibes #RoadTrip #CampLife #RockOn

Note: Later in the course, you'll learn more about prompting techniques which leverage references. 

Evaluate your output
AI tools vary in their training and capabilities. Each tool has unique strengths and limitations, which can influence the quality of their output. After receiving a response from an AI tool, it's essential to carefully evaluate the quality and effectiveness of the AI-generated content before using it or sharing the output with others.

When evaluating an output, focus on factors such as:

Accuracy

Bias

Relevancy

Consistency

AI-generated content should serve as a starting point, not a final product. Sometimes while assessing and validating an AI output, you might determine that it's unacceptable or not useful. When that's the case, you should continue on to the next step of the prompting framework.

Iterate for better results
Even well-crafted prompts may not produce ideal results on the first try. This is where iteration comes in—the process of refining your prompt based on the AI's output. Think of iteration like having a back-and-forth conversation with an AI tool. The exchange typically flows like this:

You provide an initial prompt.

The AI tool responds with an output.

You evaluate the effectiveness of the AI-generated response.

You refine your request based on what worked and what didn't.

The cycle repeats until you produce the desired results.

Effective prompting is not about getting a perfect result on the first try, but about being willing to refine and improve your approach. It's important to be patient, provide clear feedback, and keep prompting until you reach the desired outcome.

Pro Tip: When you've arrived at an effective prompt for a particular task, save it! You can use your most effective prompts as templates for different use cases and needs. This can help you replicate successful AI-output consistently—without starting from scratch each time.
   
bais, hallucination


supervised, unsupervised, reinforcement --> generative ai.

The process of training AI models
AI designers and engineers develop AI models through a process called training. Here’s an example of the typical steps a designer might take in this process, in this case for building a model that predicts rainfall:

Define the problem to be solved. 
AI designers and engineers want to predict rain to help people stay dry when commuting to and from work. They start by considering AI’s capabilities and limitations before identifying an AI solution.

Collect relevant data to train the model. 
AI designers and engineers gather historical data of days when it rained and days when it didn't rain over the past 50 years.

Prepare the data for training. 
AI designers and engineers prepare the data by labeling important features, such as outdoor temperature, humidity, and air pressure, and then noting whether it rained. It's also common to separate the data into two distinct sets: a training set and a validation set to test with later.

Train the model. 
AI designers and engineers apply machine learning (ML) programs to the prepared training data. As the ML programs analyze the data, they begin learning how to recognize patterns that indicate the likelihood of rainfall, such as the combination of high temperatures, low air pressure, and high humidity.

Evaluate the model. 
AI designers and engineers use the validation set they prepared earlier to assess their model's ability to predict rainfall accurately and reliably. Analyzing a model's performance can uncover potential issues impacting the model, such as insufficient or biased training data. If any issues exist, the AI designers and engineers may revisit an earlier step in this process to try a different approach. Once the model performs well with its validation set, the process continues to the next step.

Deploy the model. 
When the AI designers and engineers are satisfied with their model's performance, they deploy it in an AI tool—helping people in their city stay dry on their way to work!
