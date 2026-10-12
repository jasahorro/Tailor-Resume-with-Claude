<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Tailor Your Resume with Claude Dispatch

**Project Link:** [View Project](https://nextwork.ai/projects/2c615e46-1f09-5ad9-8b62-0765be0a0db6)

**Author:** Maria Jasmin Ahorro  
**Email:** jasminahorro23@gmail.com

---

![Image](https://nextwork.ai/overjoyed_magenta_proud_yak/uploads/2c615e46-1f09-5ad9-8b62-0765be0a0db6_a3f8e2r6)

## Introducing Today's Project!

In this project, I'm going to set up a powerful phone-to-desktop workflow using Claude Dispatch to streamline how I apply for jobs and manage my career materials. Specifically, I will connect my phone to my Windows laptop, give Claude access to my local project folder, and build a reusable custom Skill in Claude Desktop. This specialized Skill will allow me to instantly scrape online job posting URLs right from my phone, analyze critical role requirements, and automatically generate a precisely tailored resume, matching cover letter, and a comprehensive gap analysis saved directly to my computer.

### Key tools and concepts

The key tools I used include Claude Desktop, the Claude mobile app, Claude Code Remote Control (in place of Claude Dispatch), Claude in Chrome, custom SKILL.md configuration files, and local Markdown file management. Key concepts I learnt include cross-device remote orchestration, prompt engineering for strict factual preservation in resume tailoring, automated web scraping and job requirement analysis, structuring cover letter narratives, and extending local AI agent skills to generate tailored STAR-method interview preparation materials.

### Challenges and wins

This project took me approximately 30 minutes to complete. The most challenging part was that the Dispatch feature isn't available on my account, so I used Claude Code Remote Control as an alternative.

### Why I did this project

I did this project today to learn how to build an automated, cross-device AI workflow that connects a mobile device to a desktop environment using custom remote tools and reusable skills. Another skill I want to learn is how to set up autonomous multi-agent pipelines for automated software deployment and continuous integration testing.

## Setting Up Claude Desktop and Mobile

In this step, I'm setting up Claude Desktop on my computer and the Claude mobile app on my phone to establish the core foundation for Claude Dispatch. Specifically, I'm ensuring both applications are updated to their latest versions and signed into the same Claude Pro/Max account so they can seamlessly communicate with each other. Additionally, I'm creating a dedicated resume-project folder on my desktop via the Terminal and placing my current resume file inside it, preparing the local workspace that Claude will read from and save tailored application materials to.

![Image](https://nextwork.ai/overjoyed_magenta_proud_yak/uploads/2c615e46-1f09-5ad9-8b62-0765be0a0db6_q3j9n1w5)

### Preparing the project workspace

I installed Claude Desktop on my computer and the Claude mobile app on my phone because both applications need to be signed in to the same Claude Pro or Max account to enable Claude Dispatch to seamlessly communicate and send tasks between my devices.

![Image](https://nextwork.ai/overjoyed_magenta_proud_yak/uploads/2c615e46-1f09-5ad9-8b62-0765be0a0db6_x7p2t6a8)

## Pairing Phone and Desktop with Dispatch

In this step, I planned to set up Claude Dispatch to link the Claude app on my iPhone to my Windows laptop. Dispatch isn't available on my account, so I connected them with Claude Code Remote Control instead. I ran `claude remote-control --chrome` in my resume-project folder, then opened the Claude app on my phone, tapped Code and picked the session, which shows a computer icon with a green dot when it's online. Now I can send tasks from my phone and they run on my laptop.

This is important because I can start and check on work without sitting at my computer. Claude uses the files, apps and tools on my laptop to do the work, and I just send instructions and approve actions from my phone. It also shows that an AI agent can work for me in the background across devices, as long as my laptop stays on and awake.

![Image](https://nextwork.ai/overjoyed_magenta_proud_yak/uploads/2c615e46-1f09-5ad9-8b62-0765be0a0db6_q3n8v5x2)

### Configuring permissions and testing the connection

Dispatch isn't available on my account anymore, so I used Claude Code Remote Control instead, and I'm on a Windows laptop rather than a Mac. I enabled two things in its place: access to my resume-project folder, so Claude can read my resume and save the tailored versions there, and Claude in Chrome through the --chrome flag, so it can open job posts that need a login, like LinkedIn. My laptop has to stay awake because Remote Control doesn't run anything in the cloud. My phone only sends messages to the Claude Code session running on my laptop, which does the actual work. If the laptop sleeps or I close the terminal, the session goes offline (the green dot disappears) and my phone can't reach it.

![Image](https://nextwork.ai/overjoyed_magenta_proud_yak/uploads/2c615e46-1f09-5ad9-8b62-0765be0a0db6_w9j4t6y8)

## Building a Reusable Resume Tailor Skill

In this step, I'm going to create a reusable Skill that teaches Claude how to tailor my resume to a job posting, so I don't have to type the full instructions every time I find a new job. Since I'm using Claude Code Remote Control instead of Dispatch, I'll create the Skill in Claude Desktop's Skill editor. Skills sync to my Claude account, so my Claude Code session can use it too. Then I'll restart my Remote Control session and check that the Skill is loaded and ready, so I can send a job link from my phone and get a tailored resume back.

![Image](https://nextwork.ai/overjoyed_magenta_proud_yak/uploads/2c615e46-1f09-5ad9-8b62-0765be0a0db6_p9s1d6h3)

### Verifying the Skill in Claude Desktop

I verified the Skill by checking that resume-tailor was enabled in Claude Desktop's Skills list, and then confirming that my Claude Code session also listed it as an available skill, so I can use it from my phone through Remote Control. The SKILL.md file tells Claude to take a job posting link, read the job ad (or ask me to paste it if the page needs a login) and compare it with my base resume. It then rewrites my summary, bullets and skills to match the job's wording without making up facts or numbers. Where a number is missing, it marks the spot with [METRIC NEEDED]. It also writes a cover letter in a tone that suits the company and saves three files in my resume-project folder: the tailored resume, the cover letter and tailoring notes showing how well I match the role.

## Tailoring a Resume from Your Phone

In this step, I'm going to find a job posting on my phone and send the link to my Claude Code Remote Control session, which I'm using instead of Dispatch. That triggers the resume-tailor Skill on my laptop. Claude will read the job ad and compare it with my base resume, then write a tailored resume, a cover letter and tailoring notes into my resume-project folder. After that, I'll review the files on my laptop, fill in any [METRIC NEEDED] spots with real numbers, and adjust anything that doesn't sound like me.

![Image](https://nextwork.ai/overjoyed_magenta_proud_yak/uploads/2c615e46-1f09-5ad9-8b62-0765be0a0db6_a3f8e2r6)

### Triggering the Skill from Dispatch

I triggered the Skill by sending a LinkedIn job posting URL from my phone and asking Claude to tailor my current resume for it. Claude responded with a detailed response based on the Skill.

![Image](https://nextwork.ai/overjoyed_magenta_proud_yak/uploads/2c615e46-1f09-5ad9-8b62-0765be0a0db6_b6c9g4v2)

### Reviewing the tailored output

I compared the resumes and noticed that the tailored version keeps all my facts the same but reframes my support experience in Site Reliability Engineering terms, such as escalations, root cause analysis and runbooks. The key changes were a rewritten summary, reworded experience bullets, cloud projects and skills moved higher, customer-service metrics moved down, and less relevant skills, certificates and leadership roles removed.

## Generating Interview Prep Questions

In this project extension, I'm going to extend my Skill to automatically generate personalized interview prep questions alongside my tailored resume. Specifically, I'm updating the SKILL.md instructions to analyze key technical requirements and behavioral responsibilities from the job description, pull relevant talking points directly from my newly tailored resume, and output an interview-prep.md file featuring structured questions and STAR-method answering tips.

![Image](https://nextwork.ai/overjoyed_magenta_proud_yak/uploads/2c615e46-1f09-5ad9-8b62-0765be0a0db6_p5w9n2v7)

### Extending the Skill instructions

In this project extension, I added instructions to generate an interview-prep.md file featuring 5 personalized interview questions. The questions are based on key technical skills from the job description, behavioral responsibilities tied to the role, and relevant experience pulled directly from my newly tailored resume, complete with suggested talking points and STAR-method answering tips.

### Connecting questions to the tailored resume

In this project extension, one question asks about how I would make a third-party integration resilient. It’s a technical question the healthcare startup would likely ask, because the job involves pulling data from third-party health APIs into patient-facing dashboards.

The talking point references the failure modes I deal with every day as a Senior Support SME on the QuickBooks Connector by Intuit team. Those include expired OAuth tokens, 429 rate limits, malformed JSON payloads and data-model mismatches across 12 eCommerce connectors. 

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/2c615e46-1f09-5ad9-8b62-0765be0a0db6)*
