# Knowledge-base starter

> Kind: Kit  
> Stage: Know  
> Owner: WeGetDesign  
> Last reviewed: 2026-10-13

## Purpose

Set up a small, plain-text knowledge base for one business process, so an AI assistant can tell current, approved instructions apart from old versions and working notes.

## Linked Insight

*Knowledge before AI* (link added on publication). This playbook puts steps 1 to 3 and step 5 into practice, and supports step 6.

## Who it's for

Operations directors, technical leads and founders preparing one process for AI. You'll need someone who can decide which version of a document is the approved one.

## Time to first result

About 45 minutes for one process, if you already know where its documents live.

## What's inside

| File | What it is |
| --- | --- |
| `kb/README.md` | The rules every record follows: the header fields, the status values, how replaced records are marked |
| `kb/sources.md` | One table saying which record is authoritative for each topic |
| `kb/templates/record.md` | Blank record to copy |
| `kb/policies/`, `kb/procedures/`, `kb/working-notes/` | Fictional example records showing each status |
| `assistant/instructions.md` | Instructions that tell an AI assistant how to use the knowledge base |
| `test/ten-questions.md` | Sheet for testing the assistant against known answers before you rely on it |

## Setup

1. **Pick one process.** A client report, a task review or a policy question your team gets often. Done when: you can name the process and the person who owns it.
2. **Copy this folder** into a location your team controls. Done when: the `kb/` folder sits somewhere you can edit and back up.
3. **Delete the example records** in `kb/policies/`, `kb/procedures/` and `kb/working-notes/`, keeping the folders. Done when: only the templates and your own records remain.
4. **Add the records the process depends on,** one file each, using `kb/templates/record.md`. Fill in every header field. Done when: each record has an owner, a status and an effective date.
5. **Settle conflicts.** Where two records disagree, the owner decides which one wins. Mark the loser `superseded` and point it at the winner. Done when: no topic has two `approved` records.
6. **Fill in `kb/sources.md`.** One row per topic, naming the authoritative record. Done when: someone new could find the current instruction for each topic without asking.
7. **Give the assistant the instructions** in `assistant/instructions.md` (see "Connecting an assistant" below). Done when: the assistant can answer a simple question and name the file it used.
8. **Run the ten-question test** in `test/ten-questions.md`. Done when: a named reviewer has recorded all ten results and the fixes needed.

## Connecting an assistant

Two common ways. Neither is a security control: the assistant will see whatever files you give it, so only include records you are allowed to share with that service.

- **Claude Projects (claude.ai):** upload the files in `kb/` as project knowledge and paste `assistant/instructions.md` into the project instructions.
- **Claude Code or another assistant that reads a folder:** open the folder containing `kb/` and copy `assistant/instructions.md` into the file that assistant reads for standing instructions (for Claude Code, `CLAUDE.md`).

Other assistants can use the same records. Results vary by model and set-up, which is why step 8 exists.

## Variants

- Markdown (this folder). A SharePoint version is planned.

## What it doesn't do

- It doesn't decide which of your documents is correct. A person has to.
- It doesn't control access. Permissions belong in the system where the files live.
- It doesn't keep records current. Step 6 of the Insight (assigning a maintenance owner) is yours to do.
- It doesn't guarantee correct answers. Test before you rely on it.

## Sources and licences

All files are original WeGetDesign work. Example records are fictional.

## Licence

Documents: CC BY 4.0. Credit: *Adapted from WGD Playbooks by WeGetDesign, CC BY 4.0.*
