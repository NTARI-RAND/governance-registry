# Open questions

This folder holds open questions about this repository's own files, such as a translation, a link or how a file is laid out. Each question is one Markdown file. Together, the files are the repository's list of open questions. The list is kept up to date.

## What it is for

Keeping documents leaves questions as well as answers. A translation may not match the English, a link may break, or two files may disagree. Writing the question down keeps it from being lost. Then the next contributor can work on it.

NTARI keeps a list like this in each of its repositories. The practice comes from the Janus Facing Architecture (JFA), which asks every JFA project to keep one and keep it up to date (see the [concept triage](https://github.com/NTARI-RAND/Janus/blob/main/jfa-concept-triage-2026-08-24.md) and [Janus's own list](https://github.com/NTARI-RAND/Janus/blob/main/OPEN-QUESTIONS.md)). A question leaves the list only when it is resolved, or when the people who live with the outcome make an explicit decision about it. If this list is out of date, the repository no longer tells the truth about what is known. Check this folder whenever you send a pull request.

Bylaws §9.3 adds a rule. A question raised in governance and not resolved goes in the Institute's open-questions document, [Janus's OPEN-QUESTIONS.md](https://github.com/NTARI-RAND/Janus/blob/main/OPEN-QUESTIONS.md). Put it there, not here. Use this folder for questions about this repository's own files, such as a translation, a link or how a file is laid out.

This folder is not part of the registry. The registry is one file, [GOVERNANCE-REGISTRY.md](../GOVERNANCE-REGISTRY.md), and it is append-only. Question files are working notes, not entries, so they change as a question is answered. A question never changes an entry. If an answer shows that an entry is wrong, the Secretary adds a new entry that annotates it, and the question file links to that entry. Gaps the registry itself must show stay in the registry, under Deliberately not entered.

## Adding a question

1. Check that the question is not already listed. Look in this folder and in the other lists named above. If it is in this folder, add what you found to that file, under **What was checked**, with your name and the date. If it is listed somewhere else, add what you found there instead.
2. Create a new file in this folder. Name it with a few words from the question, using only lowercase letters a to z, digits and hyphens.
3. Copy the template below into the file, and fill in every heading.
4. Send the file in a pull request. Every commit needs a DCO sign-off: commit with `git commit -s`, which adds a `Signed-off-by` line with your name and email. This repository does not add the line for commits made on the GitHub website, so use the command line. If the DCO check fails, open its Details page.

Write in plain English. This repository is public, and deleting a file later does not remove it from the history. Never include passwords, API keys or other secrets. Apart from your own name, never include anything that identifies a person: a member's name, username or account ID, the IP address or location of someone's machine, home addresses, personal phone numbers or emails, handwritten signatures, dates of birth, personal ID numbers (such as passport numbers), bank details or donor names. Use made-up test data instead.

## Template

```markdown
# The question, in one sentence

**Status:** open

**Asked by:** your name, YYYY-MM-DD

## Why it matters

One or two sentences: what depends on the answer.

## What was checked

Each source you checked and what it showed, with its link, such as a file,
an issue, a pull request or a document. For a file on GitHub, link to a
fixed commit, not to a branch, so the link still shows what you saw. Also
say what you looked for and did not find.

## Constraints inherited

The rules any answer must respect, such as bylaws sections, governance
registry entries, the JFA's Lines That Cannot Be Crossed, or laws.
Write "None known" if there are none.

## Who might answer

For example: the Secretary, who keeps the registry (during bootstrap, NTARI's founder board), or a lawyer.

## Resolution

Leave this empty while the question is open.
```

## When a question is answered

Update its file in a pull request. Set **Status** to `resolved (YYYY-MM-DD)`, and write the answer under **Resolution**, with its evidence and links. Keep the file. The list keeps its history.

A question can also leave the list without an answer. This needs an explicit decision by the people who live with the outcome, such as the Secretary or NTARI's board. The person who asked the question cannot close it alone. Set **Status** to `closed (YYYY-MM-DD)`. Under **Resolution**, write who decided, what they decided and why, with a link to where the decision is recorded.

## Opening a question again

No answer is closed for good. Under bylaws §2.3, any member may bring a decided matter back. To reopen a question, send a pull request that sets **Status** back to `open`. Move the old **Resolution** text under **What was checked**, with its date, so the history stays. Then add the new facts, with your name and the date.
