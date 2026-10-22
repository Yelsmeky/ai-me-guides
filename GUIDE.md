# Build AI Me and grow your personal knowledge repository

The goal is to build a personal knowledge collection that an AI can use to understand your background, remember what matters to you and help you carry your thinking forward. You choose what it contains: your interests, projects, goals, preferences, decisions, lessons learned and information you want to keep. Over time, it can become a foundation for a personal AI assistant that works with a richer understanding of you.

Much of that knowledge may already be buried in your old AI conversations. You may have explained a project, worked through a difficult choice, developed an idea or researched something important—and then left the useful information scattered across chats. This guide shows you how to recover the parts worth keeping and organize them into readable, connected pages that you own and can check against the originals.

By following the guide, you will create a folder containing preserved sources, organized knowledge pages and instructions that let an AI help you use and maintain them. You could ask, “Why did I choose this approach?”, “What have I already learned about this?” or “How does this new idea connect to my existing plans?” The assistant should answer from the saved evidence and tell you when the information is missing.

**We start with existing chats because they are a useful first source. The goal is a growing personal knowledge collection.** In the future, it should also accept notes, documents, articles, recordings and other information you choose. This guide establishes the initial collection from chats; the method for bringing in those other sources is a future extension.

This guide uses **AI Me** as a working name. It builds the knowledge and memory foundation for a personal assistant. We call the organized collection of saved files a **repository**.

The repository brings two kinds of knowledge together: information about you, and information about the world that matters to you. It keeps them distinguishable. An article you save is not automatically your belief; an assistant's suggestion is not your decision; a question you asked is not proof of a lasting interest. The AI proposes interpretations and relationships with evidence, while you can correct them.

For example, old gardening conversations might initialize your garden plans and preferences. Later, soil reports, photos, planting notes and articles can update the same topics. A conversation transcript is one source; the maintained knowledge continues across sources and over time.

The organizing method is [Karpathy's LLM Wiki pattern](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f): preserve originals, have an AI maintain linked knowledge pages, and keep standing instructions for adding, questioning and reviewing that knowledge. A **wiki** is a collection of pages connected by links, so you can move from a topic to related projects, decisions or supporting sources. In AI Me, these pages hold the organized knowledge extracted from your sources. You can browse its pages, ask source-backed questions, connect ideas and develop a progressively richer picture of your interests and choices.

LLM means large language model: the AI that interprets language. The app is how you interact with it. Python is a programming language used here to automate repetitive file work. You can ask the AI to write the Python programs and explain how to run them; you do not need to learn programming before starting.

This standalone guide combines sixteen [original sources](#original-sources), including [NextWork's beginner tutorial](https://nextwork.ai/projects/3a2abc5e-4b53-4f40-abdd-c918eb780206), with official desktop and storage setup documentation linked in step 2. The first practical workflow initializes AI Me from existing chats, then records the need for an ongoing-ingestion extension. This is an adapted process, not software already installed or tested on your collection.

## Start here if you are new to this

You can begin with a ChatGPT or Claude account containing conversations you want to preserve, a computer and this guide. Step 1 obtains the exports; step 2 sets up the assistant and a persistent folder—a folder that remains available after the chat ends. The preferred setup is a file-capable desktop app working with a folder on your computer; step 2 explains how to obtain one. A supported browser connection or manual upload/download workflow is an alternative. You do not need to install a local model or one of the reference projects. Work through steps 1–5 to build and accept your first pages. You can then try step 7 immediately; step 6 expands the collection in batches when you are ready. Use it in step 7, note the future ingestion requirement in step 8, and maintain the initialized repository in step 9. App setup and obtaining exports may happen in either order; preparation needs both. You may stay in the same chat while it remains manageable.

Here is the route through the guide. You do not need to create all the files in advance; each step explains who creates them and when to continue.

| Stage | What you will have when it is finished |
|---|---|
| 1. Export | Saved copies of your conversations. |
| 2. Set up | An assistant, a tested way to save files, and a project folder. |
| 3. Prepare | Readable copies and a list of what was found or could not be converted. |
| 4. Select | Your reviewed choices about useful information in a small sample. |
| 5. Build and check | A few accepted knowledge pages and a working process. |
| 6. Repeat | More accepted pages, built in manageable batches with progress recorded. |
| 7. Use | A way to browse and ask questions of the saved knowledge. |
| 8. Plan for growth | An explanation of the future need to bring in other source types; no task to run now. |
| 9. Maintain | A way to update from later supported chat exports and preserve corrections. |

Start with one service's export if handling both at once feels complicated. You can repeat the process for the other service later, after deciding whether the same AI provider may receive both. The private local-model section is optional for this initial cloud-permitted route.

Download this guide as a Markdown file if your app offers a file-download control. Otherwise copy its full text into a plain-text file named `GUIDE.md`, or paste the text directly into the new chat. Markdown files are plain text with simple formatting marks such as `#` for a heading. Use Notepad on Windows or TextEdit on a Mac; in TextEdit choose Format → Make Plain Text before saving. Save the exact filename `GUIDE.md`, keeping the `.md` ending rather than adding `.txt`. In Notepad, choose “All files” in the Save dialog when saving a `.md` or `.py` file. If your editor changes the filename or you cannot see the ending, ask the assistant for steps for your computer before running a script. You can also paste the guide directly if saving it is unfamiliar. The original-source links are optional background; no separate research-note bundle is needed. For another AI to follow this customized process, supply this guide itself, not just a link to Karpathy.

The indented blocks beginning with “I am…” or a task request are prompts: instructions to copy into your AI conversation. Read the explanation before each one, replace bracketed placeholders such as `[folder]` with your details, and supply only the files allowed for your chosen processing route. You can ask the assistant to explain an unfamiliar term before continuing.

This guide contains the workflow to follow. The original method articles provide attribution and optional further detail; the AI can proceed from this guide without opening them. If you ask it to consult an original and it cannot, supply that text or continue with the instructions here. It should distinguish documents actually read from links merely supplied.

The supporting [download-vetting procedure](DOWNLOAD_VETTING.md) is included. The folders and files named in the steps below belong to your separate working folder, not this instructions package. Your assistant creates saved rules; its Python scripts create directories, readable copies and mechanical reports as needed, and save the LLM’s decisions and drafts. You do not need to create a folder tree or blank files in advance. Step 3 asks the AI to write the converter for your actual export; no converter is supplied here.

A few terms used below:

| Term | Plain meaning |
|---|---|
| Source ID / hash | A record label / a file fingerprint used to track records without guessing from titles. The script creates these. |
| Branch / chunk | An alternative conversation path / a bounded part of a long input that still needs its source context. |
| JSON / shard | A structured data file / one part of a split export. The script reads these for you. |
| Model inference / an inference about you / sanitization | Running a model on input / an interpretation drawn from evidence rather than something you explicitly confirmed / removing or replacing identifying details before a permitted disclosure. |
| Iterator / held-back examples | Code looping through records / examples reserved for a later test rather than used to tune instructions. |
| Metadata / manifest | Descriptive fields / a list of the source files and records being processed. |
| Endpoint / API | The address of a model service / a way for a program to call it. You do not need these for manual chat batches. |
| Checkpoint / handoff | Saved progress / a short file telling the next session what exists and what to do next. |
| Proposed / approved | Waiting for your review / accepted by you for the maintained wiki. |

## Why use both Python and AI?

An archive can contain thousands of conversations. Some work is repetitive: opening each file, following the conversation links recorded in an export, counting messages, saving readable copies and recording what finished. Other work needs understanding: deciding whether a conversation matters to you, noticing a correction, identifying a decision and combining related ideas into a useful page. We assign these two kinds of work differently.

**Use Python wherever the job can be specified as mechanical steps.** Once written, the program can repeat those steps without asking a model to reason through each operation. This avoids unnecessary AI use, reduces repeated typing and is usually quicker for routine file processing. It also saves **tokens**, the small pieces of text that models process when reading instructions and producing answers. Fewer unnecessary model requests can reduce usage limits consumed and, where requests are billed, cost. Python still uses your computer's resources, and the AI may initially help write or fix the program.

**Use AI for decisions that depend on meaning and context.** A short conversation may contain an important personal decision; a long one may be disposable trivia. A tree question might be a casual lookup or part of your long-term garden plan. A fixed word list or length cutoff cannot make those distinctions reliably for this process. The model reads the relevant source context, recommends a decision with evidence and flags uncertainty for your review. AI can make mistakes too, which is why you check a sample and retain the originals.

Python becomes a simple **driver**, also called a **harness**: it supplies the next input to the selected model, receives its answer, checks that required fields are present, saves the answer and records progress. It does not decide whether that answer is insightful or correct. Those checks need an LLM's understanding and your review. For example:

| Work to do | Who does it, and why |
|---|---|
| Count records and copy their recorded dates and IDs into an inventory | Python follows the export's structure; no language judgment is needed. |
| Decide which passages belong in your personal repository | The LLM interprets the content and your preferences; you review its recommendations. |
| Write a page explaining a decision and connect it to related knowledge | The LLM synthesizes meaning and cites the evidence. |
| Save that page, record its source IDs and check whether a linked file exists | Python performs the file operations and mechanical checks. |
| Decide whether the citation actually supports the claim | The LLM reviews the meaning; you inspect important claims. |

The goal is to avoid spending AI effort on housekeeping while keeping understanding with the AI. Savings do not come from silently skipping branches, cutting off long chats or replacing relevance decisions with rules. The model still needs the source context required for its assigned judgment. A Python driver that calls a cloud model still sends that input to the cloud; code does not remove the privacy choice below.

You can start with manual chat batches instead of an automated driver. In either case the division stays the same: **the LLM judges meaning; Python handles mechanical work.**

## Choose where the AI may process your material

Before giving an assistant your files, choose whether it may send their contents to a provider's computers. A **cloud model** runs on a service provider's computers, such as the service behind your ChatGPT or Claude account. A **local model** runs on your own computer. Keeping files on your hard drive does not by itself keep their contents local when a cloud assistant reads them. The paths below record your choice so later steps use the intended service.

**For this first round, local LLMs and local-model comparison are not prerequisites.** The starting inputs are existing ChatGPT and Claude chats: their contents have already been shared with those providers. We can use cloud models for the initial archive processing and defer local-model setup and testing until previously unshared material needs it. This guide offers that as the starting route when you permit it; it is not a privacy guarantee or a claim made by the reference authors.

| Path | Suitable material | What to do |
|---|---|---|
| **A — Cloud-permitted material** | The initial ChatGPT/Claude chats, plus later public or other material you deliberately approve for the named cloud service. | Use the approved cloud AI. Local-model setup/comparison is not required for this route; review a small working sample before scaling. |
| **B — Later material kept private** | Previously unshared documents, notes, recordings or other inputs you want to keep on your computer. | Establish local processing and test local models on their assigned jobs before processing the private collection. |
| **C — Mixed processing** | Some material may go to a cloud service; other material stays local. | Define the boundary. Local review/sanitization precedes any approved cloud disclosure. |

Already shared with ChatGPT does not mean already shared with Claude, or vice versa. You may keep each provider's chats with that provider, or deliberately approve combining them in one service. A combined archive also supplies more context in one place. Choose the intended provider/account before attaching it. This observation does not automatically cover new files or attachments whose previous disclosure is unknown.

Routing follows your permission, not the file type. An unshared article or document can use a named cloud route if you deliberately permit that disclosure; previously shared material can still be kept local if you prefer. The initial chats have the first-round choice described above. For Path A, a small end-to-end trial checks the process; it is **not a requirement to compare local models**. For Path B, capability and privacy tests remain necessary. Future batches consisting only of already shared chats may continue on Path A. Reconsider the path when the material or your preferences change, rather than merely because it is a later batch.

## 1 Gather the first sources by exporting your conversations

First, obtain a downloadable copy of your old conversations. An **export** is a package of account data supplied by the chat service. It lets you work from saved files instead of copying conversations one at a time. The download commonly arrives as a **ZIP**, a single compressed file containing other files. Keep that original package unchanged so you can recover material if a later conversion or summary is wrong.

For ChatGPT, sign in at [chatgpt.com](https://chatgpt.com). Open your profile menu, then **Settings → Data controls → Export data → Export → Confirm export**. Ensure you can receive messages at the account's email address or phone number.

OpenAI says preparation can take up to seven days. The download link expires after 24 hours; download while signed into the requesting account. Managed workspaces have different availability rules. See the [official export instructions](https://help.openai.com/en/articles/7260999-exporting-your-chatgpt-history-and-data).

For Claude, the [NextWork tutorial](https://nextwork.ai/projects/3a2abc5e-4b53-4f40-abdd-c918eb780206) describes Settings → Privacy → Export data. Verify the current menu and account availability before proceeding. Keep each service's export labeled separately; their formats differ.

Keep the ZIPs unchanged and backed up. Save them with clear labels such as `chatgpt-export-2026-10-21.zip`; record the actual date you received yours. To extract a working copy on macOS, double-click a copy of the ZIP. On Windows, right-click a copy and choose Extract All. Keep that extracted folder separate from the untouched ZIP. If extraction fails or the export has multiple/nested ZIPs, keep all originals and ask for help rather than deleting or guessing which files matter. Deleted or missing chats cannot be recreated simply by requesting an export.

**Check:** the ZIP opens, you know its service/date, and originals are separate from working files.

## 2 Set up the AI assistant and a folder for your project

You now have your exported conversations. Next, you need a place to build and keep AI Me, and an AI assistant to help you do the work. The result will be a collection of files: your preserved conversations, organized knowledge pages, instructions and records of what has been completed. You should be able to open these files yourself and return to them in a later session.

In this guide, **workspace** means the folder that holds those project files. **File access** means the assistant can open files in that folder and save new or updated files there with your permission. For example, you could tell it, “Read these exported conversations and save proposed knowledge pages in this folder.” If it has the necessary access, it can do that work directly. If it only replies in chat, you will need to upload the inputs and save its outputs yourself.

**We recommend an installed desktop app that can work with a folder on your computer.** A desktop app is a program you download and open on your Mac or Windows computer, rather than a website you open in a browser. The instructions below explain how to obtain one, choose its file-working features and connect it to your project folder. Installing the app alone does not give it access to your files; you will select the folder and check that it can read and save there.

You can also use a browser with a supported storage connection, or upload and download files manually. Those alternatives are explained below. For now, choose how the assistant will work with your files; the separate privacy choice determines which model may receive their contents.

### Obtain and open a desktop app

Before obtaining a new tool, use [DOWNLOAD_VETTING.md](DOWNLOAD_VETTING.md) with an existing assistant to review the proposed item. Supply that document when requesting the review. An allow recommendation is not installation approval.

Choose **one** of these supported routes; you do not need both apps. These are official download pages, not a request to install every tool mentioned in the reference articles. Availability, plans and menu labels can change; check the linked vendor instructions for your computer and account.

| Option | Obtain it | Start with file access |
|---|---|---|
| ChatGPT desktop with Work or Codex, where available | Go to [OpenAI's desktop download page](https://chatgpt.com/download/), choose your operating system and follow the installer instructions. | Launch the app, sign in and use a file-capable Work or Codex experience. Open/select your AI Me working folder as described in the [official app guide](https://learn.chatgpt.com/docs/app). A classic chat alone may require manual attachments and downloads. |
| Claude desktop with Claude Code | Go to [Claude's download page](https://claude.com/download), choose your operating system, open the downloaded installer and follow the prompts. See the [official installation instructions](https://support.claude.com/en/articles/10065433-install-claude-desktop). | Launch Claude, sign in, open **Code**, select the **Local** environment and select your AI Me project folder. See [Claude Code desktop instructions](https://code.claude.com/docs/en/desktop). Code access may require an eligible paid plan. |

On a Mac, open the installed app from Applications; on Windows, use the Start menu. If your operating system or account does not offer the required mode, use another supported route below. You can use another assistant, including Grok, if its actual tools meet the same requirements; the product name alone does not establish folder access or code execution.

Create an empty folder named `AI Me` in a location you can find, such as Documents. Select that folder using the app's folder/project controls and grant only the access needed for this project. Selecting a file attachment is different from granting ongoing folder access. Keep the untouched export elsewhere until the access check succeeds, then use the layout below.

**Check four separate things:** where files persist, which files the assistant can read/write, where Python actually runs, and which computer or service runs the model. A desktop app can use a cloud model. A cloud execution environment can sometimes access local files through a desktop connection. For example, [Claude Cowork's documentation](https://support.claude.com/en/articles/13345190-get-started-with-claude-cowork) describes cloud sessions with desktop-mediated local-file access; this does not establish local Python execution. For private Path B, local storage and local execution alone still do not establish local model inference.

In the app, start a new conversation using its New chat or similar control. To **attach** a file, use the paperclip, plus or Add files control and choose it from your computer; if unavailable, paste the guide text into the message. Send the setup prompt below along with the guide. This test uses invented text, so do it before giving access to real exports:

> I am setting up AI Me, a growing personal knowledge repository using Andrej Karpathy's LLM Wiki method: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f and the attached customized guide. This session is only a file-access check. My operating system is [system], my app/mode is [name], and my intended persistent project folder is [full path, or help me find it]. Read the guide; report any unavailable document. Explain which folder you can actually access, where any Python would execute, and whether model inference uses a cloud service. Do not inspect other folders, install anything or process exports. Create only SETUP_CHECK.md in the chosen folder, containing the exact sentence “AI Me setup check.” Read it back and report its actual location. If you cannot write there, say so and provide the named file for me to save; do not present an internal sandbox path as a file on my computer. Stop after this check.

Open Finder or File Explorer yourself, navigate to your chosen folder and open `SETUP_CHECK.md` in a text editor. Confirm the sentence is there. Add a second line, save it, and ask the assistant to reread the file and tell you that line. This checks both directions. If it cannot see the change, resolve access or choose the manual route before proceeding. A download link or successful preview alone does not prove continuing folder access.

### Browser and connected-storage alternatives

You can complete this process through a browser, but you must arrange persistent files yourself or use supported file tools. Browser-generated files may initially live in a remote working environment; download them into your AI Me folder. An uploaded copy does not automatically stay synchronized with your original, and a path typed into chat does not grant access to your hard drive.

- **Google Drive or another supported storage connection:** in the AI service's Apps, Connectors or Plugins settings, choose the storage service, sign in to the intended account and review the requested permissions. For ChatGPT, follow [the official Google Drive setup guide](https://help.openai.com/en/articles/10929079-google-drive-app-and-setup-in-chatgpt). Use a dedicated AI Me folder. Confirm that the connection can create, reopen and update ordinary Markdown and Python files in that folder; search/read access or editing a native online document does not prove those abilities. Account, plan and administrator restrictions may limit actions. If writing the needed files is unsupported, use manual downloads or the desktop route.
- **Browser with an explicitly supported local-folder bridge:** some agents or integrations can access a folder you select through a local companion or permission control. Follow that product's documented setup and perform the same create/read/edit check. Ordinary file upload is not such a bridge. Confirm whether the bridge supplies file access, local execution or both.
- **Manual browser workflow:** attach only the approved inputs for the current stage, ask for named downloadable outputs, and save every result into your own folder. For Python, follow step 3's local running instructions. Upload the current state files when resuming; do not assume the browser remembers your saved edits.

A Drive folder is cloud storage. If you also want normal files on your hard drive, use a supported synchronization arrangement and verify them in Finder/File Explorer. [Google explains streaming versus mirroring](https://support.google.com/drive/answer/13401938?hl=en): mirrored My Drive files have local and cloud copies, while streamed files may require downloading or offline availability. Synchronization is not a privacy boundary; it sends files to the storage provider. Do not put later local-only private inputs in a cloud-synced folder.

If direct read/write access works, continue with the opening prompt below. If you chose manual saving instead, save and reopen the test file yourself, record that the assistant needs attachments to see your edits, and continue on that basis. Whatever route you choose, your saved folder and state files—not an unsaved chat or temporary execution environment—carry the project forward.

Before using a prompt in a fresh chat, attach this guide or paste its full text, replace bracketed fields and supply the current workflow/handoff plus that stage's permitted inputs. A filename or local path alone does not give access. If a file does not exist or cannot be read, say so; the assistant should report missing state rather than assume earlier work. For initial setup, supply only this guide, without the archive. A script can inspect local files without sending them to the chat that wrote it.

The opening prompt below tells the assistant the overall goal and asks it to save the rules and starting progress. It sets up the project; it does not authorize processing the entire archive. Use your current setup chat, or start a new conversation, attach the guide, and paste:

> Help me build AI Me: a lasting personal knowledge and memory repository that can develop toward a personal AI clone. Start with my existing ChatGPT and Claude exports, but design it to grow through notes, documents, articles, recordings and other sources later. Use Andrej Karpathy's LLM Wiki method: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f, with the customizations in the attached guide. Read this guide before proposing the workflow; it supplies the complete customized instructions. The original is attribution and optional detail, not a prerequisite. If the guide is unavailable, tell me what I must supply. Do not define the product as a chat archive or reduce it to linked transcript summaries. Chats are the initial source, not the scope of the repository.
>
> Preserve original exports separately from readable sources and generated knowledge. Synthesize maintained personal-context, interest, topic, project and decision pages across sources, retaining authorship, source context, citations, disagreements and changes over time. Keep facts about me, my confirmed preferences/decisions, external knowledge and AI interpretations distinguishable; do not infer a personal belief from a saved article or casual question. An LLM judges relevance, summaries and relationships; Python only coordinates and performs mechanical checks. Use Python for repetitive file work to avoid unnecessary model requests, tokens and delay; never replace context-sensitive judgments with keyword or length rules. Keep exclusions recoverable and uncertain cases reviewable. Maintain an index, activity log and standing instructions.
>
> For this first round, the inputs are existing chats already shared with ChatGPT or Claude. Use my approved cloud provider without requiring local-model setup or comparison. Establish whether I approve combining material across providers. Retain a separate local-processing option for later previously unshared material I want private. Check a small working sample and its citations before scaling.
>
> My computer/operating system is [details]. My desired working folder is [folder]. My intended provider/account and cross-provider choice are [details or undecided]. First explain this session's actual file-access, Python-execution and file-writing capabilities. Identify any missing choices, establish permitted input/output locations and help create the guide's workspace. Save the agreed operating instructions as instructions/WORKFLOW.md and an initial progress handoff as runs/HANDOFF.md, or provide named files for me to save. Propose the small trial; do not begin full-archive processing or paid API automation.

Grant folder access through the app's controls if available. Otherwise use its attachment control, commonly a paperclip or plus button, for an approved working file. If ZIP/JSON is unsupported or too large, ask for local conversion and smaller batches. Accepting an attachment does not prove every record was read.

The project uses separate subfolders so an AI-generated draft cannot be mistaken for an original conversation or an accepted knowledge page. In the layout below, a trailing `/` denotes a folder; later, `runs/HANDOFF.md` means a file named `HANDOFF.md` inside the `runs` folder. This layout explains where future results belong. Ask the AI or its generated script to create only the directories needed for the current stage:

```text
AI Me/
  originals/       untouched exports
  sources/         readable conversations and branch metadata
  attachments/     preserved source assets
  instructions/    selection, privacy and page rules
  runs/            counts, decisions, failures and progress
  scripts/         generated Python programs
  review/          proposed changes
  wiki/            approved pages, index and activity log
```

Use the folder's actual location in prompts. On a Mac, locate it in Finder; on Windows, use File Explorer. If you do not know how to copy a full path, tell the AI your operating system and ask for the exact steps. When file access is unavailable, the AI must supply downloadable files or clearly labeled text for you to save. Download them to the named folder, or copy plain text into files with exactly the indicated names. Check that a script is really `.py`, not `.py.txt`, and a Markdown page is `.md`, not a word-processing document.

A new AI chat may not know what happened in the last one. Save the project's rules and progress in files so you can hand them to another session and continue without starting over. These are called **state files**. Keep these records with a recoverable backup of the project folder. Keep two portable state files: `instructions/WORKFLOW.md` records your processing/privacy choice, inclusion rules, page conventions and folders; `runs/HANDOFF.md` lists outputs, completed/pending/failed work and the next step. Update these at the end of each work session. A fresh chat receives both alongside this guide and the inputs for its current task. If you are just starting, tell the AI they do not exist yet; the opening prompt creates them.

These are the files that carry progress between stages. The AI and its scripts create them when their stage is reached, or provide named files for you to save. An input needed at a later stage is not a file you must prepare now. You do not need to write JSON yourself.

| File | Created or updated in | What the next session needs |
|---|---|---|
| `instructions/WORKFLOW.md` | Setup, then after changed preferences. | Folders, processing/provider choice, inclusion rules, page conventions and permissions. |
| `runs/HANDOFF.md` | Every stage. | Completed/pending/failed work, actual outputs, next step and exact files to attach next. |
| `runs/INVENTORY.json` and `runs/CONVERSION_REPORT.md` | Step 3. | Source IDs, branches/assets, source fingerprints, readable output paths and omissions. |
| `runs/SELECTION.md` | Step 4, accumulated across batches. | Each source's recommendation, reason, selected spans and your reviewed decision. |
| `runs/TRIAL_REVIEW.md` | Step 5. | Sample files, citation/question checks, corrections and your acceptance of the trial. |
| `runs/IMPORT_MANIFEST.json` and `runs/PROGRESS.json` | First trial promotion in Step 5, then every approved batch/update. | Imported source versions, derived page paths and recoverable progress for resumption/updates. |
| `wiki/index.md` and `wiki/log.md` | After page approval. | Navigation through accepted pages and a dated record of what changed. |

For Path A, state which provider/account may receive the material and whether cross-provider consolidation is acceptable. For Path B, complete the local setup below **before giving a cloud-backed agent access to previously unshared private material**. A desktop app or local folder does not establish local inference.

**Check:** you obtained a suitable app or chose a browser route; a test file persists in the intended folder; read/write capability, execution location, model location and permitted working files are known. If you chose manual saving, record that limitation in WORKFLOW.md.

## 3 Make a list of the archive and readable working copies

The export is designed for software and may be awkward to read directly. In this step, you ask the AI to write a Python program that makes an **inventory**—a list of what the export contains—and **converts** the conversations into readable text files. Conversion changes the presentation, not the meaning: it should preserve what was said and how the conversation was structured. You are not yet deciding what belongs in AI Me or asking for summaries.

Python handles this because listing, counting and copying structured records do not need a model to interpret each conversation. The program can work through the export without sending its text to an AI service. The AI writes the instructions once; the program repeats them. Later, the LLM uses the readable copies to make content decisions.

A **script** is a saved program, here a file ending in `.py`. **Running** it means telling your computer to carry out its instructions. Terminal and PowerShell are apps where you can enter the commands to do this; the prompt below asks the assistant to supply exact commands for your computer.

These mechanical steps can run entirely on your computer even when a cloud AI writes the code. If the app cannot execute locally, ask it for a downloadable `scripts/prepare_archive.py` script and a short `instructions/HOW_TO_RUN.md` file. Have it explain how to open Terminal on macOS or PowerShell on Windows, check whether Python is available, enter your actual workspace folder, run the exact command with your actual paths, and find the outputs. You do not need to improvise commands. Before running the program, ask the assistant to explain which folders it reads, which files it writes and how it leaves originals unchanged; use a working copy for the first real run.

If Python or another dependency is missing, ask for a proposed setup and explanation before installing anything. If execution returns an error, stop and share the relevant error text after checking it for personal contents; do not send the whole archive as a debugging log. Ask the assistant to create the invented example for you; you do not need to know the export format. That example checks whether the script runs and saves the expected files. It does not prove compatibility with your actual export: next compare a small converted sample from the real working copy with its original records before converting the rest. Running a script in an online notebook places its input in that environment, even if the AI calls the notebook a sandbox.

If you want conversion to stay entirely local, do not attach a private export to a cloud chat merely to get a script written. Ask for a script based on the documented format and invented examples, then run it locally. If format inspection needs a real example, decide what you permit that assistant to see first. Local Python execution does not undo an earlier upload or a cloud agent's reading of the file.

Supply the guide, existing operating instructions/handoff, and either a request for an invented example or a working copy permitted for that assistant. Then paste:

> I am preparing the first sources for AI Me, my growing personal knowledge repository, using Karpathy's LLM Wiki method: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f. Read the attached customized guide and available project instructions; report inaccessible inputs. This task is only local mechanical inventory/conversion, not semantic selection or wiki writing. Do not assume a previous chat completed setup.
>
> My operating system is [details], input location is [working copy or invented sample], and output folder is [folder]. Confirm you can access them. Write Python for execution on my computer, with no outside-service calls. Inspect the actual format, including numbered JSON shards and nested archives. Count conversations, messages, roles, dates and duplicate identifiers. Preserve IDs, timestamps, parent/child links, active branches and alternatives; never concatenate sibling alternatives into one dialogue. Inventory assets and unreadable/missing records.
>
> Have the program create its needed output directories as it works, without a template tree or manual blank-file setup. Produce readable Markdown under sources/, structured branch metadata, runs/INVENTORY.json and runs/CONVERSION_REPORT.md. Use stable IDs to prevent filename collisions; leave originals unchanged and keep raw text out of diagnostic output. Do not summarize or decide relevance. Check Python availability and explain required setup before installation. Provide scripts/prepare_archive.py and instructions/HOW_TO_RUN.md with exact OS-specific commands, expected outputs and error handling. Show how to run and verify an invented example first, then compare a small permitted real sample with its originals. Process remaining files only within my stated conversion scope; resolve unspecified scope before extending the run. If local execution is unavailable, provide the script and beginner instructions instead. Record completed, failed and pending work in a handoff file; do not claim files were saved without checking.

Markdown is readable text with simple formatting. Keep structured branch records alongside readable views. Regenerated answers and edited questions can create alternatives; Python can follow their explicit links without interpreting their meaning. Never flatten sibling alternatives into one fictitious dialogue or discard them because another branch was active. The chosen LLM interprets differences later.

Compare a normal chat, a continued chat, a branched chat and one with attachments against their originals. Record whether each asset was preserved, read or omitted from interpretation. Text conversion does not understand images, scans or audio. Failed conversions remain pending in the totals.

The [Export Parser documentation](https://github.com/temnoon/openai_export_parser/blob/master/README.md) and [Big Iron article](https://www.bigiron.cc/guides/archiving-your-chatgpt-and-claude-conversations-into-a-searchable-local-index) explain mechanics and limitations. Adapt their ideas or ask for a simpler script; installing either tool is optional.

For example, an invented report might say: “10 conversations found: 8 converted, 1 failed, 1 pending; 12 branch paths inventoried; 4 attachments preserved, 2 interpreted and 2 not interpreted.” The conversation statuses sum to 10, but conversion is not complete while two conversations remain unresolved. Preserved attachments are not automatically understood. For a long conversation, covered messages 1–40 with messages 41–60 pending is partial coverage, even if a summary exists. Bring the named report and specific failure details back to the AI, within your disclosure choice.

**Check:** counts reconcile, branches remain distinct and failures are accounted for. Open several readable files yourself. Continue with successfully converted sources only; keep failures listed as pending, and resolve them before describing the full archive as converted.

## 4 Choose which information belongs in AI Me

You now have readable source files and a record of what was converted. The next task is to separate useful knowledge from material you do not want in your personal repository. This **filtering** determines what will feed the knowledge pages; it does not delete the original archive. Decide what matters to you, then ask the LLM to recommend include, exclude or needs-review decisions with reasons. You can correct those recommendations.

For example, you might keep plans, preferences and lessons from an ongoing gardening project while excluding unrelated one-off plant definitions. A conversation can contain both: keep the useful passages with enough surrounding context to understand them. The LLM must read for meaning rather than treat every mention of plants as relevant or irrelevant.

Begin with a small **batch**, a group of conversations processed together. This lets you check the selection rules before applying them to the rest of the archive. You can attach files manually, or later use a Python driver to send each record to the selected model and save its decision. Python is the iterator—it moves through the records—but the LLM makes every filtering judgment. Path A uses your approved cloud model; Path B uses a tested local model.

**Choose manual batches or automation.** Manual batches use the chat you already have: attach a few approved converted source files, paste the selection prompt and save its decision report as `runs/SELECTION.md`. Ask the AI for a numbered list with each source ID, decision, reason and any selected spans. Correct it in ordinary language, then ask it to save your corrections in the report and `instructions/WORKFLOW.md`. Do not treat a pasted list of filenames as file access.

For an entire large archive, automation can reduce repeated attachments. It requires a program to call the selected model service, or an agent with suitable tools. Before proceeding, have the AI explain the actual access method, setup and costs. An API key is a credential used by programs; keep it out of chats, wiki pages and handoffs. A chat subscription does not establish that separate API access or charges are included. If this setup is unfamiliar, finish a manual trial first and request a specific automation plan afterward.

Supply the guide, current operating instructions/handoff, conversion report, readable source records and your inclusion preferences. Use only inputs approved for the selected model. Paste:

> I am selecting initial knowledge for AI Me, a personal repository that will grow beyond these chats, using Karpathy's LLM Wiki method: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f. Read the attached customized guide and project state. Confirm which source files, branches and coverage records are available; report missing inputs rather than infer earlier work.
>
> My processing choice is [approved cloud provider/account for existing chats, or tested local endpoint for private inputs], and my cross-provider permission is [choice]. First-round existing ChatGPT/Claude chats do not require local-model setup/testing. Do not extend that permission to previously unshared private inputs or switch providers silently. If scope, access or required API/budget choices are missing, resolve them before dependent processing.
>
> My inclusion preferences are [personalize these: useful personal context, projects, ideas, decisions, preferences, goals, lessons, continuing interests and deliberate research]. Exclude isolated definitions, trivia and casual lookups unless relevant to those interests. A random tree identification might be excluded; choosing trees for my property might belong. Have the LLM recommend include, exclude or review with a reason and source/message/branch references. Select useful spans in mixed chats, retain context and suggest combining fragments. Keep uncertainty and recoverable exclusions; never delete originals.
>
> My operating mode is [manual chat batches or proposed automation]. In manual mode, read only the attached batch and return a numbered decision report for runs/SELECTION.md; do not require an API or create a calling program. In automation mode, explain access/costs first, then write Python only to iterate, call the approved LLM, validate output shape and save decisions/progress. No keyword, length, code-count or scoring rules may decide relevance. Cover every branch and chunk; queue failures or uncovered ranges for review. Process only the supplied batch; in manual mode that may be three files. Aim for roughly ten to twenty varied conversations across the overall trial, using several small batches if necessary, and save decisions/coverage for review before scaling. If automated calls are unavailable, provide an equivalent small-batch chat workflow. Create only the directories and records needed for this batch, and save proposed decisions in runs/SELECTION.md and mark them reviewed only after my explicit response; record that response. Keep selection instructions in instructions/WORKFLOW.md and progress in runs/HANDOFF.md; if saving is unavailable, provide named files for me to save.

For a simple manual example, name the first batch `batch-001`, attach three approved converted files, and put their filenames/source IDs into the selection prompt. Have the AI return one row per source, save that result as `runs/batches/batch-001/SELECTION.md`, and incorporate your reviewed choices in the cumulative `runs/SELECTION.md`. If it cannot read one file or the response is cut off, reduce the batch and mark the unread source pending. A filename or a confident answer does not replace confirmation of which source text was read.

For the overall trial, aim for roughly ten to twenty varied conversations across as many small manual batches as needed. Review inclusions **and exclusions**, correct the instructions and try another sample when needed. Useful material late in a long chat must not be lost through opening-only classification. Keep uncertain cases pending and exclusions recoverable.

Useful patterns come from [memex](https://github.com/Simsalaba/memex-llm), [devcxl](https://devcxl.cn/en-us/blog/2026/from-chaos-to-llm-wiki-1200-conversations-distillation/) and [RayLabs](https://raylabs.app/articles/privacy-first-ai-conversation-archive/). Their rule-based shortcuts and reported totals do not establish your archive's relevance or coverage.

**Check:** decisions match your preferences, short useful chats survive and failed sections do not count as safely excluded. Tell the assistant which recommendations you accept or want changed and have it save your response in the selection report. Step 5 uses only those reviewed inclusions. If nothing in the sample belongs, choose another sample or clarify your preferences rather than force a page.

## 5 Build and check the first knowledge pages

You have selected a small set of useful source material. Now turn it into pages organized around what you want to remember, rather than one summary per conversation. A project page, for example, can bring together a goal from one chat, a decision from another and a later correction. Links connect related pages, and **citations** point back to the source passages so you can check what supports each statement.

Start with a small trial to see whether this produces knowledge you can trust and use. The AI puts drafts in `review/`. You read them, request corrections and approve specific versions before they become accepted pages in `wiki/`. Moving an approved draft into `wiki/` is called **promotion** below. This keeps unfinished interpretations out of the collection you rely on.

**Standing instructions** are saved rules the assistant should follow on every visit—for example, how to cite sources and distinguish your decisions from its suggestions. An **index** is the navigation page listing the knowledge pages; a **log** is the dated record of changes. Standing instructions may use AGENTS.md, CLAUDE.md or a document supplied to the chat. The app must actually read them; a special filename or slash command has no effect unless supported by the runtime.

There are three distinct decisions: approve which source material belongs in the wiki; accept the working trial as a method; approve specific proposed pages. A successful trial does not approve every remaining conversation or every future page.

Supply the guide, current instructions/handoff, reviewed selection decisions and the selected source records with their original context. Paste:

> Build the first linked knowledge pages for AI Me, my growing personal repository, following Karpathy's LLM Wiki method: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f and the attached customized guide. Read the supplied project state and confirm which sources are approved; do not treat raw inventory as approval or assume access to another chat. My working folder is [folder] and my permitted provider/account or local endpoint is [choice]. Resolve missing access/processing choices before reading dependent material.
>
> Use only a few approved sources for this trial. Synthesize knowledge from the first conversations into useful personal-context, preference/goal, interest, topic, project, decision, how-to, lesson and open-question pages that can later accept other sources. Keep confirmed personal information, external claims and model inferences distinguishable; a saved article is not automatically my belief and a casual question is not automatically a lasting interest. Preserve source/message/branch citations. Distinguish user statements, assistant suggestions, quotations and independently verified facts. Retain conflicts, rejected alternatives, uncertainty and later corrections. Let the LLM judge meaning and relationships; code only coordinates and checks structure. Preserve originals and make meaningful links without a quota.
>
> Save proposed pages in review/, including a proposed index.md with descriptions, log.md recording this trial, and proposed maintenance instructions in review/WORKFLOW_PROPOSED.md. Do not describe trial pages as already approved or place them in the approved wiki before review. Do not replace approved pages until their proposed changes are reviewed. Check sample claims against original messages, try a known-answer question and an unanswerable one, and report gaps. For existing approved cloud chats, no local-model comparison is required. If file writing is unavailable, supply named files for me to save. Record outputs and next work in a handoff; do not start full ingestion or claim unverified files exist.

Open the index, read pages and follow citations to their original context. Ask a known-answer question such as “What did I decide, why, and what changed later?” Also ask something the archive cannot answer. Require an honest gap rather than a plausible guess. This working trial remains necessary for cloud processing; local-model research does not.

To read the trial, open `review/index.md` in a Markdown reader or text editor. A text editor lets you inspect content even if its links are not clickable. An optional Markdown viewer such as Obsidian can open the `AI Me` folder and render page links; adopting one is a separate tool choice, not required for conversion. Ask the AI to use relative Markdown links between pages so navigation survives moving the folder.

Citations should identify a readable source file plus the applicable location: message/branch ID for a chat, page/section for a document, or time range for a recording. Add a short supporting excerpt where helpful. They should still be usable when an original provider URL is unavailable. A citation to an old assistant answer establishes what it said, not that its factual advice was correct. Label historical suggestions accordingly; verify external facts separately before presenting them as established knowledge.

To promote reviewed pages, supply the guide, workflow/handoff, selection decisions and the exact proposed batch or file list. Include review/WORKFLOW_PROPOSED.md if you want to approve its maintenance rules too. Use this in the same chat or a fresh one:

> I am approving specific knowledge pages for AI Me, my growing personal repository using Karpathy's LLM Wiki method: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f and the attached customized guide. Read the supplied workflow, handoff and review files. My permitted processing route is [provider/account or local model]. The exact proposed files/batch I approve are [list]. I accept the trial method: [yes/no, with corrections or exceptions]. Record those as separate decisions; approving pages does not by itself accept the method. Confirm these are the versions I reviewed; if their contents changed or the inputs are inaccessible, report that before promotion.
>
> Preserve originals and back up any existing pages being replaced. Promote exactly these knowledge-page versions from review/ to wiki/. If review/WORKFLOW_PROPOSED.md is included in my approved list, incorporate its accepted rules into instructions/WORKFLOW.md and record that change; do not move operating instructions into the wiki as a knowledge page. Verify relative links and source citations, update wiki/index.md and wiki/log.md, and save my separate page/method decisions, completed checks and remaining corrections in runs/TRIAL_REVIEW.md plus the handoff. Create or refresh runs/IMPORT_MANIFEST.json and runs/PROGRESS.json to include these approved trial sources, versions and page paths. Do not approve other sources, broaden provider access or begin another batch. LLMs review meaning; Python only coordinates and checks structure. If file operations are unavailable, provide precise source/destination paths and manual saving instructions rather than claim promotion succeeded.

If changes are needed, list them and request another proposal instead. A text-only chat can provide the exact approved files and a list of source/destination paths. Save or copy only those named files to their stated destinations; leave other drafts in review/. Open wiki/index.md and check that it leads to the accepted pages. Save the updated workflow, import manifest, progress record and handoff before beginning another batch; supply these current versions to a fresh chat.

**Check:** pages combine knowledge accurately, links work and claims reach the correct source context.

## 6 Process the rest of the chosen archive in batches

After you have corrected and accepted the small trial, repeat that working process for the remaining conversations you choose to include. This is the larger **ingestion** or import: bringing source information into maintained knowledge pages. It may create new pages or add evidence to existing ones. It does not mean copying every chat into the wiki.

Work in limited batches so you can review results, control any charges and recover if a session stops. A **progress record** says what is finished, failed or waiting; an **import manifest** records which source versions produced which pages. These prevent the next run from redoing completed work or forgetting incomplete work. If you choose automation, the Python driver handles that bookkeeping and repeated model calls. With manual batches, ask the assistant to save the same progress records after each batch. The LLM still selects, interprets and writes the knowledge.

For remaining material, repeat this order for each batch: **selection → review source choices → propose pages → review/promote pages → update progress**. Selection may cover the full archive first or proceed batch by batch, but page writing only uses reviewed inclusions. In the prompt below, a source not yet reviewed stays pending; return to Step 4 rather than treating the initial sample as blanket approval.

Supply the guide, `instructions/WORKFLOW.md`, `runs/HANDOFF.md`, `runs/PROGRESS.json`, `runs/IMPORT_MANIFEST.json`, `runs/SELECTION.md`, `runs/TRIAL_REVIEW.md`, the batch's approved readable sources and their conversion/coverage report, plus the current `wiki/index.md` and relevant existing pages. Those pages help the assistant enrich an existing topic rather than create a duplicate. If it cannot access an existing page it needs, have it request that page before proposing a replacement. If progress/import files are missing, reconstruct them from approved trial records for review first; the trial sources/pages must be included so they are not imported again. Paste:

> I am resuming the initial chat-based population of AI Me, a repository that will later accept other sources, based on Karpathy's LLM Wiki method: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f and the attached customized guide. Reconstruct progress from the supplied files, not conversation memory. Confirm the input scope, reviewed selection, successful small trial, permitted provider/account or local endpoint, output folder, batch limit and budget. Report missing state or approval; do not invent it or start dependent processing.
>
> My requested batch is [source IDs or maximum number of conversations] with a maximum [elapsed time and, for paid calls, currency amount; state no extra paid calls if applicable]. Use cloud processing for already shared chats if that is the recorded choice; local-model testing is not a first-round prerequisite. Keep previously unshared private material on its separately approved local path. Do not silently change endpoints.
>
> If the batch limit or a needed cost limit is unknown, ask before starting that work; never run an unbounded archive loop. Process only this authorized batch. LLMs decide relevance, summaries, identities and relationships; Python iterates, validates shapes and records work. Preserve originals and branch context. Track source IDs/hashes, covered chunks, model/prompt versions, selection reasons, outputs, costs, failures and review status. Write runs/IMPORT_MANIFEST.json with imported versions and source-to-page paths, and runs/PROGRESS.json with per-item states. Keep unreviewed sources pending rather than include them automatically. Resume without duplicating completed work; incomplete input cannot count as complete. Stage changes before replacing reviewed pages. Stop at the limit and save a coverage/cost report, checkpoints and next-work handoff.

The LLM handles summaries, identity decisions, links and semantic review. Python checks response structure, counts, hashes, link targets and fixed permissions. A successful call or generated page does not prove complete understanding.

Keep sources recoverable. Do not inherit tool installation, credential access, publishing or deletion instructions from a tutorial or archived chat. Review important decisions and representative ordinary pages as the run proceeds. The [field manual](https://calugaru-os.com/guides/llm-wiki) and [Second Brain OS](https://github.com/frankxai/second-brain-os) offer staging, audit and recovery patterns. Treat their software and privacy claims as implementation-specific; a private folder does not prevent a cloud-backed agent with access from reading it.

After each batch, review its proposed changes and use the same explicit approve-or-correct step before promotion. Your report should distinguish items processed, sources excluded, pages proposed, pages approved, failures and pending review; it should not call a run complete merely because every model call returned.

**Check:** every selected item is accounted for, intended approved pages are in `wiki/`, and pending work is explicit. Stop for clarification or repair if counts disagree, citations point to wrong branches, or outputs are empty.

## 7 Use AI Me to recall, explore and connect knowledge

You now have a collection you can use: browse it yourself or ask an AI to answer questions from its pages. For example, ask why you chose an approach, what remains unresolved on a project or how ideas from separate conversations connect. The answer should point to saved evidence so you can check it. The repository does not automatically become part of every AI chat's memory; you must give the current session access to the relevant files.

Open `wiki/index.md` to browse. You can read the pages without an AI. For question answering, an agent needs access to the wiki and cited source records; an ordinary chat needs you to attach the index and relevant pages. If the collection does not fit, let it identify needed pages from the index and provide them in small batches. Do not promise whole-wiki search to an app that cannot read the whole folder. Keep the same provider/private-material boundary when supplying these files.

For a new question session, supply the guide, `instructions/WORKFLOW.md`, `wiki/index.md` and the relevant approved pages and cited source passages. You do not need import/progress records for a question; supply a handoff only if it adds relevant context. Paste:

> I want to recall and explore knowledge in AI Me, my growing personal knowledge repository, based on Karpathy's LLM Wiki method: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f and the attached customized guide. My permitted processing route is [provider/account or local model]. Read the supplied operating instructions and permitted index, plus a handoff if relevant; list which pages you can actually access and verify that their source-derived processing restrictions allow this route. Do not assume you can search my computer or another chat. If evidence is missing, request specific permitted files rather than guess.
>
> My question is [question]. Read relevant approved pages and their underlying source passages where available. Answer with usable file/location citations, using message/branch IDs, document pages/sections or recording time ranges as appropriate; distinguish my recorded decisions, assistant suggestions, verified facts and uncertainty. Include applicable later corrections and conflicts. Say when the supplied evidence cannot answer. Do not call this a whole-archive answer if only a subset was available. LLMs judge meaning; code only coordinates retrieval and structural checks. Do not modify the wiki automatically. If the answer reveals a useful connection, gap or changed understanding that deserves a new or revised page, propose it separately for review. Distinguish my preferences and recorded decisions from external facts and your interpretations; conclusions inferred about me require evidence and an opportunity for correction.

**Check:** you can find useful pages and receive answers supported by the evidence actually available to that chat.

## 8 Future extension for ongoing ingestion

Your initial chats are a starting collection. As your interests and projects develop, you will have new information worth retaining. **AI Me needs a method for ingesting—bringing in and organizing—that new information after the initial chat-based population.** It must be able to grow as you add notes, documents, articles, recordings and other sources, enriching the same personal knowledge repository rather than creating a separate collection for each format.

The ingestion method is a future extension. Its interface, tools, supported formats and operating procedure are intentionally not specified in this guide. The present instructions initialize the repository from existing chats; they do not establish a general-purpose intake system.

When that extension is designed, it should retain source attribution, distinguish information about you from external claims and AI interpretations, and respect the processing/privacy choice for new material and its derived knowledge. A page or progress record containing private-source details needs the same local-only handling as those details, even if an earlier version was built with cloud models. Local models and their testing remain relevant when previously unshared material should stay on your computer. Existing-chat cloud permission does not automatically cover new private inputs.

## 9 Maintain and update AI Me

A useful repository needs to stay current. Later chats can change an earlier decision, answer an open question or add evidence to an existing topic. Maintenance means updating the affected pages while preserving what changed and why. Comparing a new export with the saved import record helps avoid duplicate work and accidental replacement of newer knowledge with older material.

For now, use this update procedure for later exports of the chat formats already prepared in step 3. Before running the converter again, ask the assistant to arrange separate dated output folders and exact commands that preserve prior readable source versions and reports—for example, a new sources/import-2026-11-01/ folder and runs/2026-11-01/ for that run’s reports. The date is an example; use your actual import date and a distinct folder for each run. Do not rerun an old command unchanged unless its outputs are confirmed to preserve earlier files. Convert a working copy as in step 3 and compare representative records before continuing. Adding other source types awaits the future ingestion method described above:

Supply the guide, `instructions/WORKFLOW.md`, `runs/HANDOFF.md`, `runs/IMPORT_MANIFEST.json` created during Step 5 promotion and updated in later batches, the current knowledge pages and the new source material or inventory. If an earlier import manifest is missing, ask the AI to reconstruct a proposal from preserved sources and reports for review before importing. Paste:

> I am updating the initialized AI Me repository with another supported chat export. Other source types are a future ingestion extension, based on Karpathy's LLM Wiki method: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f and the attached customized guide. Read the supplied prior import records, page conventions and handoff; report unavailable files rather than assume earlier state. My new input is [scope/location], output folder is [folder], and permitted processing route and budget are [choices]. Establish whether the input consists only of already shared chats or includes previously unshared material before model processing.
>
> Compare stable source IDs, versions and hashes without replacing newer material with an older copy. Use the already reviewed chat converter and preserve branch context. If this input requires an unsupported source format or a new intake method, report that as future extension work rather than inventing a completed importer. Show new/changed sources and gaps. Have the LLM apply the recorded relevance rules and propose affected page updates; Python only coordinates and performs mechanical checks. Preserve originals, branch context, source citations, decision history and disagreements. Already approved cloud material may retain that route without local-model comparison; new material may also use a named cloud route if I deliberately permit it. Local-only material needs the established local route and tests.
>
> Begin with a small proposed update for review. Do not infer deletion from absence in an export, publish anything or broaden provider access. Save the change report and proposed pages. After explicit approval, apply exactly the reviewed versions and update index/log, runs/IMPORT_MANIFEST.json, runs/PROGRESS.json and the handoff together, including source versions and affected page paths. Keep rejected or pending changes out of the approved state.

Periodically ask the LLM to review missing useful knowledge, unsupported claims, lost corrections, contradictions and attribution. Python can check broken links and required fields separately. Back up the whole AI Me folder, including originals, instructions, selection decisions, pages and progress. A backup is a separate recoverable copy, preferably on another storage device or a service permitted for that material. To test it, restore into a different folder and check that pages, sources and links can be opened; do not overwrite the working folder for this check.

Decide what deleting a source should do to derived pages, indexes and backups. Deletion at ChatGPT or Claude does not automatically delete local copies. Publishing or sharing the wiki is a separate choice.

Reconsider the processing path before adding a new category of material. Already shared chats may remain on Path A. Previously unshared material you want to keep private requires Path B, even if added to a wiki originally built using cloud models.

**Check:** the approved update, source versions, import/progress records and handoff agree, while pending changes remain distinguishable.

## Path B for later previously unshared material

Use this section when new inputs should stay on your computer. **It is not a prerequisite for the first archive round.** A local setup needs both software that runs a model (the **runtime**) and the model itself, which must fit your computer's available memory. This guide gives you a planning prompt rather than assuming a particular installation is suitable.

The reason for testing is practical: a model that writes convincing summaries may still miss useful passages, confuse people or overlook a later correction. Test the jobs you want it to do before relying on it. A **test example** is a small invented or permitted input with a reviewed description of what a good result should contain. **Held-back examples** are examples you save for a later check, so you can see whether improvements work beyond the cases used to adjust the instructions. An **endpoint** is the address a program uses to reach the model; record it to avoid unintentionally calling a different service.

1. Establish a local runtime/model suitable for your hardware. Record the actual model and endpoint. Verify all relevant routes—reading, filtering, summaries, images, review and later Q&A—stay local. Disable silent cloud fallback. Include logs, connected tools and backups in the privacy boundary.
2. Begin with invented or otherwise approved examples. Check that core tasks can run without network access. That checks the selected route, not every extension or historical disclosure.
3. Test each assigned job. Include short useful inputs, casual lookups, mixed topics, late corrections, ambiguous identities, long material, conflicting branches and unanswerable questions. Keep reviewed expected outcomes separate from the model and hold back examples for retesting.
4. Compare outputs, citations, omissions, speed and memory use. Local/cloud models—and different local models—do not perform equally. Summarization ability does not prove relevance, sensitivity or tool-use ability. Assign jobs based on results rather than fluent prose or self-approval.
5. Keep private Q&A local too. If sanitizing for an approved cloud step, review the output before disclosure. Removing names alone may leave identifying context.

For a fresh local setup chat, supply this guide and non-sensitive descriptions of your computer and existing software, then paste:

> I need the private-input path for AI Me, my growing personal knowledge repository using Karpathy's LLM Wiki method: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f, customized by the attached guide. This task concerns previously unshared material I want to keep on my computer. It does not revise the separate first-round choice to use approved cloud models for existing chats. Do not ask me to upload private inputs to establish the setup.
>
> My hardware/operating system and installed tools are [details]. Establish actual local inference, file/tool capabilities and all processing routes, including filtering, summaries, images, review and Q&A. Use invented examples first. Propose any missing installations for review; do not install, download models, start paid calls or enable cloud fallback without authorization.
>
> Design task-specific tests with reviewed expected outcomes and held-back examples. Include relevance, long-input coverage, branches/corrections, attribution, relationship ambiguity, privacy and unanswerable questions. LLMs judge meaning; Python only coordinates, validates shapes and logs results. Explain how to check offline operation and compare quality, omissions, speed and memory. Report limitations rather than approve a model on fluency or self-assessment. Save a setup/test plan and handoff. Run tests only when the required tools and execution/model-use authorization are established; keep private material out of this setup chat unless its route has been verified local.

Supporting references: [offline operation](https://lmstudio.ai/docs/app/offline), [model location](https://lmstudio.ai/docs/bionic/models), [scenario-based evaluation](https://github.com/seanchase-git/karpathy-wiki-mcp), and [the wiki application's separate routes](https://llmwiki.cc/docs). The application documentation describes local model slots but also an OpenRouter-specific PDF path in its release notes. Verify actual PDF routing before using private documents; a local interface alone is not proof of local processing.

Training opt-out differs from keeping input off a provider's computers; see [data controls](https://help.openai.com/en/articles/7730893-data-controls-in-chatgpt). The [research beginner tutorial](https://github.com/cnpem/sci-ai-wiki/blob/main/protocol.md) supplies a useful interview-and-first-source pattern, but its assumed skill and automatic installations are not permissions granted by this guide.

## Original sources

These are public originals, not internal summaries. You can share this guide alone; readers can follow these links for the underlying explanations. Our combined workflow, first-round cloud choice, AI Me framing and future-extension scope are adaptations rather than claims that every author prescribed the same method. Installation commands, privacy terms and supported formats can change; inspect the relevant original before adopting a specific tool.

| Source | What to read it for |
|---|---|
| [Karpathy — LLM Wiki](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f) | The preserved-source, maintained-wiki and standing-instructions pattern; ingestion, questions, maintenance, index and log. |
| [NextWork — Build an AI Second Brain with Claude Code](https://nextwork.ai/projects/3a2abc5e-4b53-4f40-abdd-c918eb780206) | Beginner setup, conversational prompts, export/conversion and a first wiki. |
| [memex-llm](https://github.com/Simsalaba/memex-llm) | Local-model triage and separate summaries with resumable processing. Its length gates, opening-only triage and flattened branches need changes for this guide's requirements. |
| [devcxl — From 1,200 Chaotic Conversations to a Personal Knowledge Brain](https://devcxl.cn/en-us/blog/2026/from-chaos-to-llm-wiki-1200-conversations-distillation/) | Selecting, combining and developing conversations into page types. Its rule-based triage differs from our LLM-owned judgment. |
| [RayLabs — ChatGPT Export: Privacy-First Knowledge Cards](https://raylabs.app/articles/privacy-first-ai-conversation-archive/) | Private originals, selected knowledge, sanitization and separate review before external use. |
| [Second Brain OS](https://github.com/frankxai/second-brain-os) | Export intake, distillation, citations, audit trails and verification. Folder separation alone does not establish local inference or isolation. |
| [Calugaru OS — Build Your Own LLM Wiki](https://calugaru-os.com/guides/llm-wiki) | Eight chapters covering sources, page design, ingestion, retrieval, maintenance, access, evaluation and recovery. Mechanical teaching examples do not prove semantic quality. |
| [Sci AI Wiki — Beginner Tutorial](https://github.com/cnpem/sci-ai-wiki/blob/main/protocol.md) | Interview-driven research setup, page conventions and single-source ingestion. It assumes a supplied setup skill and additional tools. |
| [OpenAI Export Parser — README](https://github.com/temnoon/openai_export_parser/blob/master/README.md) | Export layouts, media restoration and readable local views. Retained raw JSON and a branch-aware interpretation remain important; viewer scripts may use external CDNs. |
| [Karpathy Wiki MCP](https://github.com/seanchase-git/karpathy-wiki-mcp) | Scenario-based local-model evaluation, fictional fixtures and human inspection. A source marked ingested is not proof of complete understanding. |
| [Big Iron — Archiving Your ChatGPT and Claude Conversations Into a Searchable Local Index](https://www.bigiron.cc/guides/archiving-your-chatgpt-and-claude-conversations-into-a-searchable-local-index) | Python/SQLite importing and search. Its example deliberately keeps the current branch rather than every alternative. |
| [OpenAI — Exporting your ChatGPT history and data](https://help.openai.com/en/articles/7260999-exporting-your-chatgpt-history-and-data) | Official export request, eligibility, download and troubleshooting instructions. |
| [OpenAI — Data controls in ChatGPT](https://help.openai.com/en/articles/7730893-data-controls-in-chatgpt) | Training controls, temporary chats and distinctions between privacy settings. |
| [LM Studio — Offline Operation](https://lmstudio.ai/docs/app/offline) | Which local model/document operations can work offline and which acquisition/update tasks require connectivity. |
| [LM Studio — Choose a Cloud, Local, or Remote Model](https://lmstudio.ai/docs/bionic/models) | Where inference happens and why a desktop application can still use cloud or another-device processing. |
| [LLM Wiki application documentation](https://llmwiki.cc/docs) | Separate model routes for ingestion, questions, chats, review and images; verify each relevant route for private use. |
