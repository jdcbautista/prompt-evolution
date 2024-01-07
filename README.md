# Prompt Evolution

Let's apply the techniques and concepts we covered earlier today to iterate and refine a series of prompts.

We'll start with a topic of your own choosing, then we'll move onto some common use case scenarios.

Typically, you'll want to create as few prompts as possible to conserve resources and time.  By carefully considering your request, you'll know based on the amount of detail and quality you're looking for, whether to draft and submit a zero-shot, one-shot, few-shot, Chain-of-Thought, or five element prompt (role, task, background, example, output).  With an effectively crafted prompt, there may not be a need for refining and iterating.

For the purpose of this first exercise, let's assume you're still in the research and discovery phase of your project, so time and cost aren't large concerns.

We'll use the free public version of ChatGPT, which runs on  GPT-3.5 Turbo.

## Prework:

A large part of developing your proficiency as a software engineer revolves around practice and repetition.  You should have noticed by now that the entire curriculum is formatted as a large Github repository.  This was deliberately done to provide you with daily exposure to Github, and to provide you with daily opportunities to practice interacting with the Github Command Line Interface.

To help Github CLI become second nature, use each challenge as an opportunity to practice the Github workflow.

### Project Set Up

1. Fork the challenge repository through the Github browser UI
2. Clone your fork to your local machine by copying your fork's URL through the Github browser UI and in your terminal command line, running `git clone <fork-url>`
3. Copy the URL of the source repository through the Github browser UI, and use this to set your remote upstream by running in your terminal command line `git remote add upstream <source-url>`
   * By default, your local clone's remote origin will be set to the URL from which it was created, in this case, your fork.  You'll also want to add a remote upstream connection to the source URL.  In a real world scenario, this allows you to quickly fetch any changes pushed to the source repository in between when you last updated your local clone and now.  If you don't fetch these changes, you may be prevented from pushing your own changes.

### Creating Changes

1. In your terminal, Switch to a new branch using `git checkout -b <branch name>` (Make it a habit to always begin changes on a new branch to prevent accidentally pushing changes to a shared branch like `main` in a real world setting)
2. Add or update the code changes you need to create using your text editors.
3. Once you're ready to stage your changes to a commit, add the files you want to push using `git add <filename>`.
   * Using `git status` makes this step much easier, as the status will return a list of all the files that you've modified, and whether or not they've been added to your commit.
4. Once you've staged your commit by adding all the files you want to push, use `git commit -m <brief message describing the nature of your commit>`.  
   * In a real world scenario, your team or organization may have their own set of standards regarding best practices on commit messages.  Some examples: 'username/minor/brief-description', 'directorypath/servicename/brief-description' 
5. Once you've made your commit, run `git push origin <branch name>`.
   * You can use `git status` to double check what branch you're currently in
   * Being out of sync with the source repository may prevent you from pushing changes.  Use `git fetch upstream main` to fetch the latest branch & commit history from the source repository's main branch.
   * There may be times where fetching the latest branch & commit history is not enough to sync up your clone to the source repo.  You may have to use `git pull upstream main` to pull in the actual file changes.  Depending on your local configuration, this may potentially overwrite any changes you have made locally.  With the default Github CLI configurations, you will have a chance to interactively review change conflicts between all incoming changes and your local changes.  When you confirm the pull, files with change conflicts will open up in your VS Code text editor, and you'll be able to visually compare differences in the code.
6. Once you've pushed your changes, review the Github CLI output to find a URL.  Command or control clicking this URL will open up the Github UI in your browser, where you'll be able to create your Pull Request.

For this challenge, once you've cloned your fork of the source repo onto your local machine, CCD (change directory) into the "solutions" directory `cd solutions` and create a new file using your first name initial and last name.  Make it a markdown file by using the .md extension.  Example: `touch saltman.md` or `code saltman.md` if you've set up the VS Code alias.

> Tip:  VS Studio gives you the option of setting up a `code` command that will create or open files from the command line.  https://code.visualstudio.com/docs/setup/mac

Once your file is set up, use Markdown syntax to format your prompts and LLM outputs.  Learning Markdown syntax will benefit you as a software engineer as Markdown is commonly used when writing documentation.

Example:

```markdown
// Hashes are used to format headers, with the number of hashes referring to the header style used (H1, H2, H3, etc.)

// Markdown accepts HTML tags.  For this exercise, we'll use the <blockquote> tag to format quotes.  If you aren't familiar with HTML tags, we'll cover them later in the curriculum.  Just know for now that HTML utilizes tags to determine how elements in a web page are rendered, and that tags always compose of an opening tag using the tag name (ex: <blockquote>) and a closing tag using a forward slash in front of the tag name (ex: </blockquote>).

// When generating a table, highlighting the table in the ChatGPT UI won't work.  Use the clipboard button to copy the table.  Also, you won't want to use <blockquote> </blockquote> for rendering tables in Markdown because Markdown handles table rendering automatically in the format given to you by the clipboard button.  You can paste the table as is, and if you want to go the extra step of beautifying it, insert a Greater Than / Right Carrot character (>) at the start of each line of the table 👌.

// In programming languages such as Javascript, double forward slashes indicate comments within a script, and as such are ignored by the compiler.  These comments here are for your own benefit.  The lines below are the actual example of what your Markdown file syntax will look like.

## Step 1

Prompt:
<blockquote>
(Copy and paste your prompt here)
</blockquote>

Output:
<blockquote>
(Copy and paste the LLM output here)
</blockquote>

```

## Step 1: Zero-shot prompt

With a topic of your own choosing, consider what you'd like to ask ChatGPT.  In your ChatGPT thread, let's intentionally retrieve a quick and unbiased response by omitting as much detail as possible. 

### Example:

Prompt:
<blockquote>
How much wood could a woodchuck chuck if a woodchuck could chuck wood?
</blockquote>


Output:
<blockquote>
The phrase "How much wood would a woodchuck chuck if a woodchuck could chuck wood?" is a tongue twister and a playful, humorous question rather than a serious inquiry. It's meant to be a wordplay and doesn't have a definitive answer. The purpose is to create a challenging sequence of sounds that can be difficult to pronounce quickly and accurately. If you're looking for a humorous response, you might say, "A woodchuck would chuck as much wood as a woodchuck could chuck if a woodchuck could chuck wood!"
</blockquote>

## Step 2: One-shot prompt

Let's now introduce an additional element of data.  In our example we're going to add a layer of data by suggesting that the woodchuck can chuck one chunk of wood per pound of body weight.

### Example:

Prompt:
<blockquote>
How much wood could a woodchuck chuck if a woodchuck could chuck wood and the woodchuck was capable of chucking one chunk of wood per pound of the woodchuck's body weight?
</blockquote>


Output:
<blockquote>
The question now adds an interesting twist by suggesting that the amount of wood a woodchuck could chuck is somehow related to its body weight. However, it's important to note that woodchucks are not known for chucking wood in reality; they are ground-dwelling rodents and don't have the physical ability to engage in such activities.

If we were to entertain the hypothetical scenario presented, the amount of wood a woodchuck could chuck would still depend on the woodchuck's body weight. Without a specific weight provided for the woodchuck, it's impossible to determine an exact amount. You could define a relationship, such as "one pound of wood per pound of woodchuck," but again, it's all part of the playful and humorous nature of the original tongue twister.
</blockquote>

## Step 3: Few-shot prompt

Let's now introduce a second additional element of data.  We're now going to specify how much the woodchuck actually weighs.

### Example:

Prompt:
<blockquote>
How much wood could a woodchuck chuck if a woodchuck could chuck wood and the woodchuck was capable of chucking one chunk of wood per pound of the woodchuck's body weight and the woodchuck weighed between ten and twelve pounds?
</blockquote>


Output:
<blockquote>
Even with the additional information about the woodchuck's body weight being between ten and twelve pounds and the hypothetical scenario of chucking one chunk of wood per pound, the question remains largely playful and humorous. The specific amount of wood a woodchuck could chuck in this scenario is still subjective and doesn't have a practical answer.

If you want to go along with the whimsical nature of the question, you could say something like, "If the woodchuck weighs ten pounds, it could chuck ten pounds of wood, and if it weighs twelve pounds, it could chuck twelve pounds of wood." Remember, this question is meant for amusement, and the goal is not to arrive at a precise or realistic answer.
</blockquote>

## Step 4: Adding Exceptions

Is there anything in the LLM's response output to your prompt that you find extraneous?  In our example, the LLM continues to reiterate how this scenario is hypothetical.  We add the instruction to refrain from commenting in regards to the scenario's hypothetical nature.

### Example:

Prompt:
<blockquote>
How much wood could a woodchuck chuck if a woodchuck could chuck wood and the woodchuck was capable of chucking one chunk of wood per pound of the woodchuck's body weight and the woodchuck weighed between ten and twelve pounds?

Ignore the fact that this is a hypothetical scenario, and refrain from commenting in regards to the hypothetical nature of this scenario.
</blockquote>


Output:
<blockquote>
If we take the given hypothetical scenario at face value and consider the woodchuck's body weight as between ten and twelve pounds, we can calculate the potential amount of wood it could chuck.

For a woodchuck weighing ten pounds, it could chuck ten pounds of wood. For a woodchuck weighing twelve pounds, it could chuck twelve pounds of wood. In this specific scenario, the amount of wood chucked corresponds to the woodchuck's body weight.
</blockquote>

## Step 5: Adding Exceptions as a List

The LLM still couldn't help but mention that the scenario was hypothetical.  In our example, we returned the question to its simplest form and provided the additional elements as a list of rules.

### Example:

Prompt:
<blockquote>
How much wood could a woodchuck chuck if a woodchuck could chuck wood?

Let's establish some ground rules:

1. Ignore the fact that this is a hypothetical scenario, refrain from mentioning that this scenario is hypothetical.
2. Provide the answer as chunks of wood instead of pounds of wood.  Assume a woodchuck is capable of chucking 2 chunks of wood per pound of body weight.
3. Assume the woodchuck weighs between nine and thirteen pounds.

</blockquote>


Output:
<blockquote>
In adherence to the specified conditions:

If a woodchuck is capable of chucking 2 chunks of wood per pound of body weight, and it weighs between nine and thirteen pounds, the woodchuck could chuck between 18 and 26 chunks of wood.
</blockquote>

## Step 6: Chain of Thought Prompting

Practice giving the LLM some more complex instructions.  Consider the amount of detail you need to provide for each step.  In our example, we gave a complicated word problem that resulted in an incorrect response.  It took a few fine-tunings of the prompt to correcet the LLM.

### Example:

Prompt:
<blockquote>
Q:  Consider a family of two woodchucks.  A papa woodchuck that is 18 pounds can chuck 3 chunks of wood per pound of body weight every minute for 10 minutes, and 2 chunks of wood per pound of body weight every minute for 5 minutes after before having to rest for 30 minutes until it can repeat this process.  A mama woodchuck is 14 pounds, and can chuck 2 chunks of wood per pound of body weight for the entire 15 minutes before it has to rest for 30 minutes.  How many chunks of wood can this family of woodchucks chuck over the course of one hour?

A:  In the first 15 minutes, the 18 pound papa woodchuck will chuck 720 chunks of wood (3 chunks * 18 pounds * 10 minutes = 540 chunks of wood and 2 chunks * 18 pounds * 5 minutes = 180) before having to rest for 30 minutes.  It can then chuck another 720 chunks of wood in the last 15 minutes of the hour, for a total of 1480 chunks.  The mama woodchuck will chuck 420 (2 chunks * 14 pounds * 15 minutes) in the first 15 minutes, and another 420 in the final 15 minutes after resting for 30 minutes, for a total of 840.  By combining the number of chunks the papa woodchuck can chunk in one hour (1480) to the number of chunks the mama woodchuck can chunk in one hour (840), we can confirm that this family of woodchucks can chunk  a total of 2320 wood chunks over the course of one hour.  

Q:  Consider a family of three woodchucks.  A papa woodchuck that is 19 pounds can chuck 3 chunks of wood per pound of body weight every minute for 10 minutes, and 2 chunks of wood per pound of body weight every minute for 5 minutes after before having to rest for 30 minutes until it can repeat this process.  A mama woodchuck is 15 pounds, and can chuck 2 chunks of wood per pound of body weight for the entire 15 minutes before it has to rest for 30 minutes.  They also have a teenage 8 pound woodchuck that can chuck 1 chunk of wood per body weight per minute for 20 minutes before having to rest 20 minutes until it can resume chucking wood.  How many chunks of wood can this family of woodchucks chuck over the course of one hour?

</blockquote>


Output:
<blockquote>
Papa Woodchuck (19 pounds):

First 15 minutes: 3 chunks * 19 pounds * 10 minutes = 570 chunks
Next 5 minutes: 2 chunks * 19 pounds * 5 minutes = 190 chunks
Rest for 30 minutes
Last 15 minutes: 3 chunks * 19 pounds * 10 minutes = 570 chunks
Total chunks in one hour for Papa Woodchuck: 570 + 190 + 570 = 1330 chunks

Mama Woodchuck (15 pounds):

First 15 minutes: 2 chunks * 15 pounds * 15 minutes = 450 chunks
Rest for 30 minutes
Last 15 minutes: 2 chunks * 15 pounds * 15 minutes = 450 chunks
Total chunks in one hour for Mama Woodchuck: 450 + 450 = 900 chunks

Teenage Woodchuck (8 pounds):

First 20 minutes: 1 chunk * 8 pounds * 20 minutes = 160 chunks
Rest for 20 minutes
Last 20 minutes: 1 chunk * 8 pounds * 20 minutes = 160 chunks
Total chunks in one hour for Teenage Woodchuck: 160 + 160 = 320 chunks

Now, let's find the total number of chunks for the entire family:

1330 chunks (Papa) + 900 chunks (Mama) + 320 chunks (Teenage) = 2550 chunks

So, the family of three woodchucks can chuck a total of 2550 wood chunks over the course of one hour.
</blockquote>

The LLM didn't understand that for the Papa woodchuck, the first 15 minutes should contain both the formula for the first 10 minutes of full woodchucking capability and the following 5 minutes of reduced woodchucking capability.  Simply telling the LLM `Your math is wrong for the papa woodchuck` resulted in the LLM apologizing but returning the exact same incorrect answer.

We had to apply further Chain of Thought prompting to teach the LLM the nature of its mistake.

Prompt correction 1:
<blockquote>
Your math is wrong for the papa woodchuck because you're counting 10 minutes for the first 15 minutes in the first formula.  The first fifteen minutes should contain both the 10 minute formula and the 5 minute formula.

</blockquote>

Prompt correction 2:
<blockquote>
This is still incorrect, because you didn't correct the last 15 minutes.  Remember, when fully rested the papa woodchuck can chuck 3 chunks for 10 minutes of the 15 minute window before slowing down to 2 chunks for five minutes of the last 15 minute window.

</blockquote>

Output:
<blockquote>
I appreciate your patience. Let's correct the calculation for the Papa Woodchuck:

Papa Woodchuck (19 pounds):

First 15 minutes: (3 chunks * 19 pounds * 10 minutes) + (2 chunks * 19 pounds * 5 minutes) = 570 chunks + 190 chunks = 760 chunks
Rest for 30 minutes
Last 15 minutes: (3 chunks * 19 pounds * 10 minutes) + (2 chunks * 19 pounds * 5 minutes) = 570 chunks + 190 chunks = 760 chunks
Total chunks in one hour for Papa Woodchuck: 760 (first 15 minutes) + 760 (last 15 minutes) = 1520 chunks

I apologize for the confusion in my previous responses, and I appreciate your diligence in catching that error.

</blockquote>

## Step 7: Five Element Prompting

Now practice a prompt where you provide a Role, Task, Background, Example, and Output. Refer to today's lesson if you need reminders for what these specifically entail.

Our example:

<blockquote>
Role:  You are world famous broadcaster and biologist David Attenborough in a world where woodchucks are capable of chucking two chunks of wood per pound body weight per minute.  You are narrating a segment on a new episode of Planet Earth showcasing the magnificence of two woodchuck parents teaching their woodchuck child how to chuckwood.

Task:  You are observing a family of three woodchucks chucking chunks of wood.  Write a compelling narrative in the style of the narration on the television series Planet Earth describing the scene of an 18 pound papa woodchuck, 14 pound mama woodchuck teaching their 5 pound baby wood chuck how to chuck wood over the course of 15 minutes.

Background:  Drama is unfolding as the baby woodchuck struggles to chuck wood at the same rate the parents can chuck wood for the first 10 minutes.   The audience is at the edge of their seat, wondering if the baby woodchuck can ever chuck wood as quickly as its parents.  At the end of the segment, the audience must be impressed by the record number of wood chunks chucked by this precious family of woodchucks.

Example:  Intro: The typical woodchuck weighs anywhere between ten and twenty pounds.  Yet they are capable of chucking two chunks of wood for every pound of body weight they possess.  Few special animals in the world are capable of such a feat.  But such a feat does not come naturally.  Young wood chucks often struggle to to chuck wood as effectively as their full grown parents. 

Output:  Write out the narrative script for this segment following the Classic Story Structure of an intro, Rising Incident, Climax, and Ending Resolution.
</blockquote>

<blockquote>
[Opening Scene]

David Attenborough (voiceover): "In the vast woodlands of North America, a remarkable family of woodchucks embarks on an extraordinary journey. The woodchuck, a creature known for its burrowing abilities, reveals a hidden talent – the art of chucking wood. A family, consisting of an 18-pound papa woodchuck, a 14-pound mama woodchuck, and their curious 5-pound offspring, is about to showcase the wonders of woodchuck life."

[Rising Incident]

David Attenborough (voiceover): "The sun casts a golden hue upon the tranquil woodland, where our woodchuck family has gathered to pass on a crucial skill – the art of chucking wood. Papa woodchuck, with his impressive 18-pound frame, and mama woodchuck, slightly lighter at 14 pounds, demonstrate the intricate technique with effortless precision. The little one, a mere 5 pounds, observes with wide-eyed fascination. However, the challenge lies ahead."

[Transition to Action]

David Attenborough (voiceover): "As the family begins its wood-chucking demonstration, drama unfolds. The baby woodchuck attempts to match the pace of its parents, but the smaller size and inexperience become apparent. For the first 10 minutes, the young woodchuck struggles to keep up, eliciting a collective gasp from the audience. Will it overcome the odds and master the art of chucking wood?"

[Climax]

David Attenborough (voiceover, with heightened excitement): "Tensions rise as the baby woodchuck grapples with the demanding task. The parents, ever patient and encouraging, guide their offspring through each chuck, demonstrating the skill that defines their species. The audience is at the edge of their seat, witnessing a crucial moment in the woodchuck family's journey. Can the little one rise to the occasion?"

[Resolution]

David Attenborough (voiceover, with a triumphant tone): "In a heartwarming twist, as the clock ticks toward the 15th minute, the baby woodchuck begins to find its rhythm. The struggles transform into determination, and the little woodchuck starts to chuck wood with increasing confidence. The parents, beaming with pride, watch as their offspring not only catches up but surpasses expectations. It's a triumphant moment for the entire woodchuck family."

[Total Chunks Chucked]

David Attenborough (voiceover, with a reveal): "And so, as we reflect on this spectacular family spectacle, let's marvel at the astounding feat they've achieved. Over the course of these 15 minutes, the woodchuck family, working together in harmony, has collectively chucked a remarkable 225 chunks of wood. A true testament to the strength, unity, and resilience of the woodchuck family in the heart of the North American woodlands."

[Closing Scene]

David Attenborough (voiceover): "From the 18-pound patriarch to the resilient 5-pound offspring, this woodchuck family has not only mastered the art of chucking wood but has left an indelible mark on the very fabric of their woodland home. Their story, a lesson in determination and familial bonds, echoes through the trees and serves as a reminder that even the smallest among us can achieve greatness."
</blockquote>

## Additional Exercises

In the time remaining, pick and choose from the following and try to return as many solutions as you can.  Some of these may cover topics that you are not yet familiar with, and as such may be too challenging at the moment.  

Just as with the above exercise, copy and paste your prompts and outputs into your Markdown file.  If you find yourself needing to refine and interate through multiple prompts, choose the most relevant ones to demonstrate the evolution of your prompts (ex: beginning, middle, end).

### Easy:

- Have ChatGPT generate a reference sheet for Github CLI commands.  Consider how you want this data organized to generate the most value.

- You want to create a quick reference sheet for what methods to use to convert various data types in Javascript vs. Python.  Ask ChatGPT to create a table for you, so that you'll know what method to use if you wanted to:
    1. Convert strings to integers
    2. Convert integers to strings
    3. Create an array of strings
    4. Create a key/value pair of strings to integers
    5. Convert an object to JSON

- You are working with a third party API.  You need to retrieve an order ID from the URL returned to you from an endpoint.  Ask ChatGPT to provide you the **Regular Expression** to use to extrapolate an object ID from this URL:  https://exampleapi.com/orders/products/23475098258/bol.json

- You're prepping for job interviews and you want to understand Big O notation.  How can you utilize ChatGPT to help you achieve this?  Consider your prompts carefully.

- Ask ChatGPT to help you prep for the Whiteboarding portion of a code interview.  Ask it for a whiteboarding challenge, and work through that challenge as if ChatGPT were your interviewer.

### Hard:

- You're working on browser based game or app prototype and you want the ability to navigate a 4x4 grid of cells.  Ask ChatGPT to create this functionality for you.  The end result should be that you can run this script from your console and see it working in your browser.  (Hint, ask to use the Three JS library)

- You land at a software company that embraces infrastructure as code and DevOps philosophies.  As such, the infrastructure team doesn't provision resources for you, but instead, provides the teachings and resources to software engineers so that they can provision their own resources using Terraform.  Use ChatGPT to help you quickly understand what Terraform is, and how to write a terraform configuration to help you host your application on AWS.

- You want to be able to quickly push changes to your application in a development environment.  Ask ChatGPT to help you understand how to utilize Github Actions to do this.  (Hint: You'll eventually learn that an application typically consists of a client-facing front end, a server-side back end API, and a backend database.  You'll also learn that deploying an application consists of containerizing the app and choosing where to host your containerized application.  Providing details regarding these elements to ChatGPT will help it generate a configuration file for you)
