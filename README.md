# ApplyKoala MCP server

A remote MCP server for your job search. Connect **Claude Code**, **Codex**, **Claude** or **ChatGPT** to it, and your AI saves the jobs it finds, researches companies with sources, keeps your interview stories and tracks every application in your own [ApplyKoala](https://applykoala.com) job tracker. The next conversation starts where the last one ended.

- **Address:** `https://applykoala.com/mcp` (Streamable HTTP)
- **Sign-in:** OAuth 2.1 with dynamic client registration. You add the address, a page opens, you sign in and press Allow. No API key.
- **Official MCP Registry:** `com.applykoala/mcp`
- **Docs and setup page:** https://applykoala.com/mcp

This repository holds the documentation only. The server is hosted by ApplyKoala; there is nothing to install or run yourself.

## Connect it

### Claude Code

```sh
claude mcp add --scope user --transport http applykoala https://applykoala.com/mcp
```

Then type `/mcp` in Claude Code and sign in.

### Codex

```sh
codex mcp add applykoala --url https://applykoala.com/mcp
codex mcp login applykoala
```

The second command signs you in.

### Claude (web, desktop or phone)

Settings → Connectors → Add custom connector, and paste `https://applykoala.com/mcp`. Free plans can add one custom connector.

### ChatGPT

In a web browser, open chatgpt.com/plugins (on a phone, switch to the desktop site), choose **Add → Add custom MCP server**, paste the address, keep OAuth and press **Connect**. The phone app cannot add it, but uses it once it is added. In a chat, type `@applykoala`. Step by step: https://applykoala.com/guides/chatgpt-job-search

New to Claude Code or Codex? [How to install them, no coding needed](https://applykoala.com/install-claude-code-or-codex).

Other AI tools that connect to remote MCP servers with OAuth may work too, but we have not tried them.

## Things to say to your AI

- "Find backend jobs in Singapore that fit my resume and save the good ones."
- "Look into these three companies. Do they sponsor work visas?"
- "Save the recruiter in this screenshot and what we talked about."
- "I have an interview at Harbourline on Friday. Which of my stories fit the job?"
- "Give me a mock interview for that job."
- "Here is the recording of today's interview. Debrief it and save the notes."
- "What is waiting for a reply this week?"
- "Move my job search from this spreadsheet into ApplyKoala, with the dates."

## Tools

| Area | Tools |
|---|---|
| Start | `get_overview`, `get_help`, `set_tips` |
| Jobs | `search_jobs`, `get_job`, `save_job`, `update_job`, `set_job_fit` |
| New jobs from company career pages | `get_job_alerts`, `update_job_alerts`, `get_new_jobs`, `get_job_posting`, `follow_company` |
| Companies | `search_companies`, `get_company`, `save_company`, `add_company_research` |
| Applications | `list_applications`, `record_application`, `record_applications`, `get_apply_kit`, `record_unmatched_message` |
| People | `search_contacts`, `get_contact`, `save_contact`, `log_interaction` |
| You | `get_profile`, `update_profile`, `list_resumes`, `get_resume`, `save_resume` |
| Stories | `search_stories`, `get_story`, `save_story` |
| Interviews | `get_interview_questions`, `save_interview_questions`, `start_practice`, `record_practice`, `get_practice_progress`, `save_practice_topic`, `update_practice_settings`, `record_interview_debrief`, `get_interview_debriefs`, `play_the_interviewer` |
| Posts | `list_posts`, `get_post`, `save_post` |

### Prompts

Ready-made tasks your AI client can show as commands:

| Prompt | What it does |
|---|---|
| `get_started` | Look at what is in ApplyKoala and set you up |
| `find_jobs` | Search the web for jobs that fit your profile and save the good ones |
| `research_company` | Research a company and save the findings with sources |
| `analyze_fit` | Compare a job with your profile and save the take |
| `prepare_application` | Draft a cover letter and form answers from your real experience |
| `save_person_from_chat` | Read a chat screenshot and save the person and the main points |
| `story_bank` | Go through your experience and save the stories you can tell in interviews |
| `prepare_stories` | Pick the stories that fit a job and help you tell each one |
| `mock_interview` | Practise an interview for a saved job or with common questions |
| `play_the_interviewer` | Role swap: you ask the questions, the AI answers as the candidate |
| `prepare_answers` | Write answer points for interview questions from your own stories |
| `interview_debrief` | Go through a real interview and save short notes on it |
| `write_post` | Write a short post from your real stories, for LinkedIn or another site |
| `weekly_review` | What happened this week and what to do next |

## Rules the server gives your AI

- **Your real experience only.** Fit notes must quote your profile, resume or stories word for word; ApplyKoala rejects quotes it cannot find.
- **Sources for research.** Every company finding needs a source URL and the date it was checked.
- **Postings word for word.** Pay, seniority and deadlines are filled in only from the posting.
- **It never submits for you.** ApplyKoala's tools do not submit applications. If your AI has its own browser (for example Claude Code or Codex with a browser tool), it asks you before each submission by default.
- **Nothing is deleted for good.** Changes to your details are shown to you first, and earlier versions are kept for 30 days.

## Privacy

- Your AI sees only your own ApplyKoala: jobs, companies, applications, people, your details, resumes and stories.
- What it reads is sent to the company that makes the AI, under their privacy policy.
- Disconnect it any time in ApplyKoala: Settings → Use ApplyKoala with your AI.
- Full policy: https://applykoala.com/privacy

## Price

ApplyKoala itself is free in the browser, with no account. The MCP server reads and writes your data on ApplyKoala's servers, so it needs sync: free for 7 days with no card, then US$3.99 a month or US$29 a year. See https://applykoala.com/pricing.

## Questions and problems

Open an issue in this repository, or write to contact@applykoala.com.
