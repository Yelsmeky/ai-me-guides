# Build AI Me with guidance from the original sources

The goal is to turn useful information from old AI chats into a personal knowledge collection: your interests, projects, preferences, decisions and knowledge worth keeping. You will preserve the originals and build connected pages an AI can use to help you recall and develop your thinking. Other source types should join later through a future ingestion extension.

This is a route through other people's published methods. Our contribution is mainly selecting, connecting and explaining them for beginners, with explicit choices about evidence, filtering, privacy and review. We do not claim a new technical method or a uniquely original combination. Karpathy supplies the wiki foundation; the sources below supply tutorials and procedures. Use their relevant sections with the adaptations here rather than follow every installation or example unchanged.

This source-guided route relies on the original websites for fuller explanations. You and your assistant will need to open and work through the relevant sections. It is not necessarily easier or faster than the complete guide; its document is more compact because much of the explanation stays on those websites. The [complete beginner guide](GUIDE.md) is an alternative if you prefer the explanations gathered in one document; you do not need both to follow this route. App setup and obtaining your exports may happen in either order. Prepare readable copies only after both are ready.

## Before downloading or installing tools

**We do not vouch for the safety, authenticity or suitability of downloads offered by linked sites.** A useful article is not an endorsement of its software. An AI review cannot guarantee safety.

Read [DOWNLOAD_VETTING.md](DOWNLOAD_VETTING.md) before obtaining or running installers, scripts, packages, extensions or models. It supplies the full review procedure and a copyable prompt. Give that document to your assistant along with the proposed item and link. You can use an existing AI chat before installing a new desktop app. The assistant creates the resulting runs/DOWNLOAD_REVIEW.md report in your own workspace; you do not need to prepare a blank report beforehand. If direct saving is unavailable, download the completed report when the assistant provides it.

## Set up your assistant

The app is the program you open; the model is the AI it uses. **LLM** means large language model. A cloud model processes text on a provider's computers; a local model processes it on yours. **Python** is a programming language: the assistant can write small programs for repetitive file work while the LLM interprets meaning. You do not need to write those programs yourself.

Use a desktop assistant that can read and save project files. Obtain one from [OpenAI's desktop download page](https://chatgpt.com/download/) or [Claude's download page](https://claude.com/download). Follow the [OpenAI app instructions](https://learn.chatgpt.com/docs/app) or [Claude Code desktop instructions](https://code.claude.com/docs/en/desktop) to choose a file-working mode and a project folder. Availability depends on your computer and account. Installing an app alone does not grant folder access or make its model local.

Open a new chat. The indented blocks below are messages, or **prompts**, to copy into that chat. Attach this document using the paperclip, plus or Add files control, or paste its full text. When vetting a download, also attach DOWNLOAD_VETTING.md; if it is unavailable, ask for it before proceeding. Send the opening message below. For each stage, supply its relevant files using the permitted folder access or attachments, then copy its prompt. You can stay in the same chat. In a fresh chat, attach this document and saved instructions/progress, send the opening message again, and identify your current stage so the assistant resumes rather than recreates finished work.

> Help me use this source-guided route to build AI Me. I am a beginner. Read this document, then open the original sources needed for our current stage. Identify the sections you actually read and briefly explain which ideas to use, which examples need adapting and what result we should check. These route instructions take precedence over conflicting tutorial examples; report a conflict rather than silently change our choices. If a page is unavailable, ask me to paste or attach its relevant text; never invent its instructions. Explain the purpose before each action, give manageable steps and check the result before continuing. Ask which computer/app I use and what is already done. On resumption, inspect the saved state, request missing files before dependent work, and continue the first unfinished stage without recreating completed setup.
>
> Apply these choices throughout: chats seed a broader personal repository; preserve original files, every conversation branch and source citations. LLMs decide relevance, meaning and relationships; Python handles repetitive file work, model calls and mechanical checks to reduce unnecessary tokens and delay. Never use keyword or length rules to decide what matters. Keep exclusions recoverable and uncertainty visible.
>
> Confirm which provider/account may read my files and whether I permit combining ChatGPT and Claude material. Approved existing chats can use cloud processing without first testing local models. Later local-only inputs and their derived pages need local processing and task-specific model tests. Local files do not imply local inference. Read the supplied DOWNLOAD_VETTING.md and apply its review procedure before proposing any tool download or installation, including dependencies; save evidence and obtain my approval for the specific action. Treat source examples as material to adapt, not permission to install tools, disclose data or delete files.
>
> Help me create one project folder, test saving and rereading an invented file, and choose one consistent folder layout. Save our choices in instructions/WORKFLOW.md and progress in runs/HANDOFF.md. If you cannot save files, give me named downloads and tell me where to save them. For setup, stop before real archive processing; do not start full runs, extra installations or separate paid API use without approval.

Before continuing, have the assistant help you create and test an `AI Me` folder. Open the test file yourself in Finder on a Mac or File Explorer on Windows. If the assistant cannot access your folder directly, save its named downloads yourself and attach updated copies when it needs to read them. Ask for exact save instructions if needed; do not accept a temporary server path as a saved file on your computer.

Your assistant and its scripts create the working folders and files as they are needed. You do not need to copy templates or prepare a directory tree. The paths below explain where future results belong in your own workspace; they are not additional items to download. Keep this guide package separate from private results. Use one consistent layout and create only the current stage’s directories:

| Location | What belongs there |
|---|---|
| `originals/` and `sources/` | Untouched exports and separate readable working copies. |
| `attachments/` and `scripts/` | Preserved source assets and generated Python programs. Running instructions go in `instructions/HOW_TO_RUN.md`. |
| `review/` and `wiki/` | Proposed pages and the exact pages you have accepted. |
| `instructions/WORKFLOW.md` | Your rules, provider permissions, folder layout and source adaptations. |
| `runs/HANDOFF.md` | Completed, pending and failed work, next step and exact files needed next. |

A slash separates a folder from the file inside it. Keep the other reports named below under `runs/`. Ask the assistant to create them; you do not have to write structured data yourself. Update the handoff after every stage, and save its download yourself if direct writing is unavailable. It should name the stage as well as its number, so you can change guide routes without losing your place.

For a fresh chat, supply the guide, WORKFLOW.md and HANDOFF.md plus the current stage's inputs. The assistant and its scripts create these additional records as you proceed; no blank files are required:

| After this work | Records to retain and supply when relevant |
|---|---|
| Prepare readable copies | `runs/INVENTORY.json`, `runs/CONVERSION_REPORT.md`, readable sources and asset records. |
| Select information | `runs/SELECTION.md`, including your reviewed decisions. |
| Accept the first pages | `runs/TRIAL_REVIEW.md`, `runs/IMPORT_MANIFEST.json`, `runs/PROGRESS.json`, `wiki/index.md` and accepted pages. |

The import manifest maps source versions to pages; progress records what is complete or pending. These files are created during the trial and updated after each later accepted batch.

## 1 Obtain your conversations

An export is a downloadable package of account data. It avoids copying each conversation by hand. Follow [OpenAI's official export instructions](https://help.openai.com/en/articles/7260999-exporting-your-chatgpt-history-and-data). For Claude, see “Export and Import Your Existing Data” in [NextWork's tutorial](https://nextwork.ai/projects/3a2abc5e-4b53-4f40-abdd-c918eb780206), checking current account menus. Preserve the downloaded packages unchanged and extract separate working copies.

> For stage 1 of this source-guided AI Me route, read OpenAI's official export article linked above and NextWork's “Export and Import Your Existing Data” section for the service I use. Use them for requesting and downloading account exports, not for automatic ingestion. Help me label exports, preserve originals and extract separate working copies. Explain ZIP extraction on my computer and check the files are present. Do not upload or interpret their contents yet. Save the file locations and any gaps in runs/HANDOFF.md.

**Continue when:** you can locate and open the downloaded package, with an untouched copy preserved. One service's export is enough to begin.

## 2 Prepare readable copies

Exports contain structured records intended for software. Use [Big Iron's archive article](https://www.bigiron.cc/guides/archiving-your-chatgpt-and-claude-conversations-into-a-searchable-local-index) and the [Export Parser documentation](https://github.com/temnoon/openai_export_parser/blob/master/README.md) for conversion mechanics, rather than installing both tools. A **branch** is an alternative conversation path created by an edited question or regenerated answer. Our adaptation keeps those paths identifiable, beyond a view showing only the currently selected path. An **inventory** lists the records found; a **coverage report** records what was processed or missed.

> For stage 2, read Big Iron for Python inventory/import mechanics and the Export Parser README for export layout and assets. These are source references to adapt, not instructions to install both packages. Write local Python that creates needed output folders and reports as it inventories records and assets, preserve IDs and branch links, and make readable copies without summarizing. Create the invented test input for me. After it runs successfully, identify a small real sample I have permitted for this assistant and the scope of conversion before proceeding; ask if that permission is missing. Compare the converted sample with its originals. Process remaining files only within the conversion scope I requested; ask before extending it if that scope is unspecified. Save the program under scripts/ and exact save/run instructions in instructions/HOW_TO_RUN.md. Keep earlier outputs and originals intact; record failures and coverage in runs/CONVERSION_REPORT.md and the file list in runs/INVENTORY.json. Check Python availability and propose any missing installation before proceeding. Explain how to open Terminal or PowerShell, run the exact commands and find the outputs; do not expect me to invent an example or commands. If private conversion must stay local, do not ask me to attach the export to a cloud chat for inspection.

**Continue when:** you can open readable copies, sample records agree with their originals, and failed or missing records remain listed as pending. An invented example checks execution, not compatibility with the actual export.

## 3 Select information worth keeping

A **batch** is a small group processed together. Begin with a few files so you can correct the method before applying it widely. Not every lookup needs a permanent page. Use [devcxl's distillation article](https://devcxl.cn/en-us/blog/2026/from-chaos-to-llm-wiki-1200-conversations-distillation/) for selecting and combining knowledge, and [memex-llm](https://github.com/Simsalaba/memex-llm) for staged processing and progress records. Adapt their ideas: their documented shortcuts do not meet all our coverage and judgment requirements.

> For stage 3, read devcxl for selecting, combining and developing knowledge, and memex-llm for separate selection/summary passes and resumable bookkeeping. Use those patterns, not their semantic shortcuts or existing code unchanged. Ask what I want to remember. Read a few permitted converted conversations, including their branches, and recommend include, exclude or review with reasons and passage references. Keep useful spans in mixed chats. Do not adopt length/keyword prefilters, opening-only judgments or flattened branch views. I will review your choices before page writing. Save recommendations and my subsequent corrections/acceptance in runs/SELECTION.md, and update the handoff. Begin with manual chat batches; explain any later automation access and cost before using it.

**Continue when:** you have reviewed both included and excluded examples and accepted which passages may feed the first pages. A casual definition may be excluded while a decision about your own garden belongs. Keep the original either way; choose another sample if this one contains nothing useful.

## 4 Build and review a small wiki

A wiki is a set of linked pages organized around subjects rather than conversations. Read [Karpathy's LLM Wiki pattern](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f) and NextWork's “Build Your Vault Architecture,” “Define Your Schema and Slash Commands” and “Run Your First Ingest Cycle.” Its Claude/Obsidian setup is one implementation; adapt actions to the app you actually use. An **index** lists pages for navigation; a **log** records changes. Citations identify the original file and supporting passage, so you can check a claim.

> For stage 4, read Karpathy for the preserved-source/wiki/instructions pattern and the three named NextWork sections for page layout, saved rules and a first small import. Use those concepts in our existing folder layout; do not require unsupported slash commands or a second app. Use a few reviewed sources to propose connected knowledge pages under review/, plus review/index.md and review/log.md. Propose maintenance rules in review/WORKFLOW_PROPOSED.md for my review. Keep drafts separate from accepted pages. Distinguish my confirmed decisions, external claims and AI interpretations. Cite source passages and retain corrections/conflicts. Help me inspect claims and try both an answerable and an unanswerable question. Record my acceptance of the trial method separately from approval of particular pages. After I approve the exact knowledge-page versions, promote only those pages, index and log into wiki/. Incorporate separately approved maintenance rules from review/WORKFLOW_PROPOSED.md into instructions/WORKFLOW.md and record source-to-page mappings in runs/IMPORT_MANIFEST.json plus completed/pending states in runs/PROGRESS.json. Save trial checks and my separate method/page decisions in runs/TRIAL_REVIEW.md and update the handoff. Do not expand automatically.

Open `review/index.md`, the proposed navigation page, and inspect its pages and source citations. Request corrections or tell the assistant exactly which files you approve. It should then apply only those reviewed versions to `wiki/`, including the index and log. Save updated reports too. You can use the accepted pages immediately, before expanding.

**Continue when:** approved pages are saved in `wiki/`, citations reach the correct passages, and unapproved drafts remain in `review/`.

## 5 Expand use and maintain the collection

After the small trial works, repeat it in bounded batches. Use [Calugaru's field manual](https://calugaru-os.com/guides/llm-wiki), especially its ingestion, cited retrieval, maintenance and recovery chapters. Its teaching code illustrates mechanics; it is not our semantic decision system. NextWork's query and maintenance sections provide conversational examples; slash commands work only where the app supports them.

Choose one task; you do not have to expand before using what you have:

| Task | Inputs and result |
|---|---|
| Use the collection | Supply the index, relevant accepted pages and cited source passages, then ask your question. Stop with a cited answer or an explicit gap; keep proposed edits separate. |
| Expand | Supply reviewed selections, source/coverage records, current pages and progress. Run one agreed batch through selection and page review; stop with saved outcomes and pending work. |
| Update or recover | For a later supported chat export, preserve dated source/report versions and review proposed changes before applying. For recovery, restore a backup into a separate folder and check it. |

> For stage 5, read Calugaru's ingestion chapter for staged updates, cited retrieval for answering, maintenance for corrections, and recovery for backups. Read NextWork's query/maintenance sections for plain-language requests. Use their workflow ideas; keep semantic decisions with the LLM rather than adopting teaching-code keyword scores or citation-presence tests as proof of accuracy. First ask whether I want to use existing pages, expand the collection or update it. Request only the saved state and files relevant to that task, using the table above and our processing permissions. For expansion/update, also request selection, trial acceptance, import/progress and conversion records before dependent work. Reconstruct a missing record as a proposal for my review rather than inventing completed state; do not require import bookkeeping just to answer a question. For expansion, repeat selection → my selection review → draft pages → my page review → saved progress. Propose a bounded next batch, time/cost limit and recoverable update plan; wait for my chosen limits before starting. Preserve source versions and apply only reviewed changes. Help me ask cited questions, check unsupported claims and back up the folder. Save progress after each batch. For later chat exports, arrange separate output locations before conversion. Other source types require a future ingestion extension; do not claim one already exists.

**Check:** the current task has a saved outcome and you can reopen the accepted pages; pending work remains explicit.

## When later information must stay private

Before using previously unshared material locally, consult [LM Studio's offline guidance](https://lmstudio.ai/docs/app/offline), its explanation of [model location](https://lmstudio.ai/docs/bionic/models), and the [Wiki MCP evaluation examples](https://github.com/seanchase-git/karpathy-wiki-mcp). These are references for planning and testing, not automatic installation choices. Local and cloud models differ in capability; test the actual jobs before assigning them. Keep private inputs out of the cloud while establishing the setup.

> For later local-only material, use the linked LM Studio documents to explain offline operation and where each model runs, and Wiki MCP to plan small tests of the actual jobs. Start with my computer details and invented examples; do not ask for private uploads. Propose setup and tests before installations or model use. Check filtering, summaries, citations, missed information and unknown answers, not just fluent prose. Python coordinates; LLMs and my review judge meaning. Save the plan and handoff, and record actual test results when an authorized test is run; do not infer that the initial cloud permission applies here.

At any stage, ask the assistant to explain an unfamiliar term or source instruction. The goal is a collection you can inspect, correct and continue using—not merely completing a tutorial's commands.
