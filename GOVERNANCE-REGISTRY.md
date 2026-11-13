# NTARI Governance Registry

**Authority:** Bylaws [P1-001 v1.0](https://github.com/NTARI-RAND/bylaws/blob/main/P1-001_Bylaws_v1.0.md) §9.5 · **Keeper:** the office of the Secretary (§8.4); during bootstrap the founder board holds the function (§16.1) · **Opened:** 2026-09-08

The public, append-only registry §9.5 requires. It records recognitions and lapses of membership, the publications of Article XI, expulsions and readmissions and re-entries under Article XII, and each amendment of the official document and of these bylaws. Acts taken while the founder board exercises the powers of the membership are labeled **bootstrap acts** under §16.1, so they are findable rather than folklore.

**Two rules govern this file itself.** It honors the privacy floor of §2.4: parties are identified by role and by reference, never by personal information beyond what the proceeding requires. It is append-only under §2.5: an entry is corrected by a later annotating entry, and no entry is deleted or rewritten. Every act recorded here remains valid and remains open to the membership under §2.3.

**Interim form, with a committed exit.** This Markdown file is the interim document form of the registry. Its intended mechanical form is the policy register in the record machinery — versions committed to the record plane, digests and identifiers in the commons under line 7, with claim discovery through the register read. That component is unbuilt. The committed exit: when the policy register ships, the entries below migrate into it and this file is retained as the historical record of the interim period rather than deleted. Until then a reader should treat this as a filing cabinet that is honest about being one.

**Provenance, stated plainly.** This file was opened on 2026-09-08 and was not kept contemporaneously before that date. Entry 1 is entered retrospectively and labeled as such, sourced to the instrument's own designation rather than to a contemporaneous record. Nothing here is backdated: the entry date is the date of the act, and the recording date is given where the two differ. Acts deliberately not entered are listed at the end, with the reason, so an omission is visible rather than silent.

---

## Entry 1 — Adoption of the bylaws, P1-001 v1.0

| | |
|---|---|
| **Date of act** | 2026-08-31 |
| **Recorded** | 2026-09-08 (retrospective; see Provenance) |
| **Type** | Bootstrap act — adoption of a governance instrument |
| **Authority** | §16.1 (founder board exercising the powers of the membership); recorded under §9.5 |
| **Status** | Valid; open to the membership under §2.3 |

The founder board prepared and adopted [P1-001 Bylaws v1.0](https://github.com/NTARI-RAND/bylaws/blob/main/P1-001_Bylaws_v1.0.md), the first bylaws instrument written to the Janus Facing Architecture. Version numbering was restarted at 1.0 as a deliberate lineage restart; the P1-001 v6.0 through v8.0 line was archived to the [Historical Docs](https://github.com/NTARI-RAND/bylaws/tree/main/Historical%20Docs) folder of the bylaws repository rather than amended.

**Source of this entry.** The instrument designates itself, in its own header and at §16.1, as prepared and adopted by the founder board as a bootstrap act and recorded in the governance registry under §9.5. This entry makes that designation true in fact. It is entered from the document, not from a contemporaneous minute, and a reader should weight it accordingly.

---

## Entry 2 — Amendment of the official document and its invariant registry: residential substrate posture

| | |
|---|---|
| **Date of act** | 2026-09-08 |
| **Recorded** | 2026-09-08 |
| **Type** | Bootstrap act — amendment of the official document (§9.2) and of the invariant registry (§9.16) |
| **Authority** | §9.2, §9.16, §16.1 |
| **Raised by** | The office of the Vice President (Calvin Secrest), in the board's September 2026 review of the official document |
| **Status** | Valid; open to the membership under §2.3 |

**What was amended.** The Substrate layer's protocol tier of [the official document](https://github.com/NTARI-RAND/Janus/blob/main/janus-facing-architecture.md) gained one paragraph:

> Nodes join that market over encrypted overlays and outbound polling, without requiring open inbound ports or a static address; the connection as a residential provider ships it is enough. Line 11 depends on this: a substrate that ran only where a provider permits inbound service would carry a chokepoint at every provider.

**Why.** Consumer broadband carries dynamic addresses, sits behind carrier-grade network address translation, and bars inbound servers by policy. A substrate that required inbound service would run only where a carrier permits it, making every carrier a veto — a chokepoint per provider, distributed in appearance and centralized in fact, which line 11 forbids. The reference protocol's node-side operations already poll rather than listen; the amendment commits the property so it cannot be lost in a refactor.

**Registry change under §9.16.** One invariant added:

| Identifier | Section | Binding | Anchor |
|---|---|---|---|
| `SUB-no-inbound-requirement` | Substrate | implementation | "without requiring open inbound ports or a static address" |

No invariant was retired and no identifier, anchor, or binding was altered. The identifier is newly issued and has never been issued before, as §9.16 requires; it does not descend from a retired invariant, so no lineage is recorded. It is reported delegated and unbound under §9.15 until a repository ships tests citing the identifier — proving a node completes register, heartbeat, poll, run and report with no listening socket, no static address, and a translated changing address in front of it.

**The §9.2 precondition is satisfied.** The conformance suite passes against the amended text: all nine document checks pass, the registry carries 26 invariants with every anchor present in its own section, and 23 of the 26 are reported delegated and unbound. The count published with this run under §9.15 is 3 bound, 23 unbound. Reproducible by anyone under §9.17:

```bash
python jfa-conformance-suite.py   # from a checkout of NTARI-RAND/Janus
```

**Companion records updated in the same act.** The [structure article](https://github.com/NTARI-RAND/Janus/blob/main/jfa-structure-article.md), whose stated invariant count moved from twenty-five to twenty-six; all seven language renderings of the official document under P2-002, with the source snapshot date moved to 2026-09-08; [OPEN-QUESTIONS.md](https://github.com/NTARI-RAND/Janus/blob/main/OPEN-QUESTIONS.md) entry 9, which records the constraint, the resolutions, and what remains open, per §9.3. The concept triage record was not amended, because nothing it retired was reintroduced and §9.2's triage condition is therefore not engaged.

**Standing decision recorded with the act.** Carrier constraints are treated as an immutable adversarial physical constraint, to be routed around in code rather than negotiated through law or regulation. Lobbying may proceed as a civic matter and this decision takes no position against it, but it is never a dependency of the architecture and no deployment plan may assume its success. The reasoning and its empirical basis are set out in the companion whitepaper [P1-004 v0.1](https://github.com/NTARI-RAND/Janus/blob/main/P1-004_Substrate-Constraints_v0.1.md), issued as a draft with this act.

**What this act did not adopt.** The whitepaper's posture on the remaining two constraints is argued, not bound, and no part of it is registered:

- **Bandwidth asymmetry** — small coordination traffic under line 7, work shipped as sandboxed modules rather than machine images, and locally spooled jobs. Recorded as design posture only. The module-over-image default is not registered, because the reference implementation does not satisfy it today.
- **Hardware confidential execution** — redundant execution across independently assigned hosts with covenant-rated disagreement, data minimization as the primary control, and attestation as an optional priced capability, in place of any enclave requirement. A candidate identifier, `SUB-redundant-execution`, is named in open question 9 and is **not issued**; whether to register it is a decision for the board under §9.16, and registering it would oblige the substrate to build a work-type it has not built.

**Referred, not decided.** Whether compensated participation on a residential line engages the non-commercial prong of typical carrier acceptable-use policies is a question of contract terms in a jurisdiction, which no protocol design answers. It is referred to counsel, to travel with the business-use insurance questions already pending for the combined heat-and-compute pilot. Until it is answered, prospective node hosts should be told what participation may mean for their own service agreement.

---

## Entry 3 — Agrinet federation sync: per-peer authentication, scheduled import kept on

| | |
|---|---|
| **Date of act** | 2026-11-04 |
| **Recorded** | 2026-11-06 (two days after the act; see Source) |
| **Type** | Bootstrap act — choice between two conflicting implementations of a federation policy |
| **Authority** | §16.1 (founder board exercising the powers of the membership, since no federation exists yet to decide); recorded under §9.5 |
| **Decided by** | The President (Jodson Graves), for the founder board |
| **Raised by** | Two open pull requests to [NTARI-RAND/Agrinet](https://github.com/NTARI-RAND/Agrinet) that set opposite federation policies on the same files: [#197](https://github.com/NTARI-RAND/Agrinet/pull/197), from the office of the Vice President (Calvin Secrest), and [#194](https://github.com/NTARI-RAND/Agrinet/pull/194), from an outside volunteer contributor |
| **Status** | Valid; open to the membership under §2.3. Not yet carried out: neither pull request had merged when this entry was recorded |

**What was decided.**

1. #197's federation stance stands. Agrinet nodes keep a scheduled federation import, and peers authenticate to each other with per-peer HMAC signatures, with signed exports checked against the node registry.
2. #194 rebases onto #197 and keeps its cursor pagination. Its competing model (one shared read-only export key, with scheduled import switched off) is not adopted.
3. One condition attaches. Because scheduled import stays on, #197 must not merge until its import of peer listings and transactions stops overwriting local rows (item 2 of the same review). As written, that import replaces a local transaction's escrow, party and dialog fields with the two fields a peer sends.

**Why.** Both designs were offered as the way Agrinet nodes exchange data, and they could not both land. With no federation yet constituted under §16.1, there was no membership body to choose between them, so the founder board chose.

**What this act did not decide.** Reputation still crosses as one number: `reputationScore` appears in the public user record and in the federation export, which JFA line 8 forbids ("Reputation is never one number"). The same review names this as a separate open question, and this act takes no position on it.

**Source of this entry.** The decision was announced as item 10 of the President's review requesting changes on #197, posted [2026-11-04 at 19:30 UTC](https://github.com/NTARI-RAND/Agrinet/pull/197#pullrequestreview-5774516560) against head commit `3f8c128`. That review is the contemporaneous record. This entry was made from it two days later, after the 2026-11-06 open-PR triage found the decision missing from this registry.

---

## Entry 4 — Annotation of Entry 3: the import condition on Agrinet #197 is waived

| | |
|---|---|
| **Date of act** | 2026-11-06 |
| **Recorded** | 2026-11-07 |
| **Type** | Bootstrap act — annotation of Entry 3 (§2.5: corrected by a later entry, not by rewriting) |
| **Authority** | §16.1; recorded under §9.5 |
| **Decided by** | The President (Jodson Graves), for the founder board |
| **Status** | Valid; open to the membership under §2.3. Not yet carried out: #197 had not merged when this entry was recorded |

**What changed.** Entry 3's third point said #197 must not merge until its import of peer listings and transactions stops overwriting local rows. That condition is waived. #197 may merge with the overwrite unfixed. Points 1 and 2 of Entry 3 stand unchanged.

**Why.** The Institute is in bootstrap, building its core systems before opening them to the public. The President directed that #197 be merged.

**What the waiver leaves open.** Merging #197 turns on Agrinet's six-hourly federation import. While no peer node is registered, the import has nothing to pull, so the overwrite cannot occur. Once any peer is registered, a two-way sync replaces local transactions with stripped copies, losing their escrow, party and dialog fields. The overwrite therefore has to be fixed before the first peer is admitted. This entry does not change the separate requirement that every commit carry a DCO sign-off; that check has no bypass.

---

## Entry 5 — Audio Arts Academy seed entered as the Institute's advice to a partner organization

| | |
|---|---|
| **Date of act** | 2026-11-07 |
| **Recorded** | 2026-11-07 |
| **Type** | Bootstrap act — entry of an Economy & Information seed, and of the advice it carries, into the Institute's record |
| **Authority** | §16.1 (founder board exercising the powers of the membership); §9.6 (conformance named self-attested); recorded under §9.5 |
| **Decided by** | The President (Jodson Graves), for the founder board |
| **Disclosure (§14.3)** | The President prepared the seed and advises the partner organization on it. That authorship is disclosed here. |
| **Status** | Valid; open to the membership under §2.3 |

**What was decided.**

1. The Audio Arts Academy seed is entered as an Economy & Information seed of the Institute, of the teaching-studio exchange shape, at proposal stage. It consists of the plan of 2026-10-25 as revised on 2026-10-29 and 2026-11-07, its open-questions document, its conformance self-description, and its stewardship and tax research note. Its conformance is self-attested under §9.6: it has no code and no tests. The conformance suite's project checks pass against it.
2. The plan is the Institute's advice to a partner: a Florida recording-studio owner forming a separate nonprofit, the Academy, beside the owner's for-profit studio. Every decision in the plan belongs to the partner and to the Academy's own board. The Institute takes no seat, vote, custody or approval role in the Academy, and is never a counterparty, custodian or clearer in its exchanges (§9.7, §10.7).
3. Joining JFA's Economy & Information layer is recorded as a long-term proposal to the Academy, not a condition of the advice. The Academy's board alone decides it, at the plan's phase 4, once four stated conditions hold. Two of those conditions fall on the Institute and are listed below as not decided.
4. A reading of §3.2(b) is adopted for this seed. The duty to label oneself unfederated binds an instance. While the Academy runs its own system, which is not JFA software (forms and a spreadsheet), it makes no JFA or federation claim and labels what it issues "self-attested" only. From the day it runs JFA's session software until every condition of §3.2 holds, it labels everything "self-attested; unfederated". This reading is made for this seed alone; a seed that runs JFA software from its first day is not affected.

**The purpose, as the President stated it.** To support a capable partner in running a nonprofit in the way that returns the most to the community it serves, with a culture of software development driving that community's work of producing human music.

**The limits the advice keeps on that purpose.** They are recorded with it so that a later reader does not stretch it.

- *The return goes to the community, never to insiders.* "Most profitable" means the most training and recording for each dollar and volunteer hour. The plan meets it by paying every money cost from donations and grants, handing out studio time by a fixed amount and a public draw, and keeping the partner's for-profit studio separate, with any lease at or below fair market value and the partner stepping out of every vote on it. A 501(c)(3) may not pass its earnings to insiders.
- *Software is the culture, not the charitable purpose.* The culture shows in how the Academy works: published rules, an append-only record, reproducible draws and shared copyleft tools. The Academy's articles name no software purpose, because IRS denial letters through February 2026 lean against counting the maintenance of open code toward exemption (plan chapter 6; the seed's research note). Reusable session code would be the Institute's to steward, not the Academy's.
- *Human music is claimed only as far as the record shows.* The session record attests that people were present at a dated session and that the files are unchanged since. It does not, and cannot, prove that no machine made the audio.

**What this act did not decide.**

- Acceptance of any session code (the fingerprint tool, the verifiable draw, form templates) into NTARI-RAND. That waits on the Institute's counsel answering item 9 of the 2026-08-25 counsel memo, and on a separate recorded decision (the seed's open question 18).
- Whether an Academy that runs only free sessions, on the session software as published, meets the operator duties of §10.2. That is for the membership to confirm, and it is one of the plan's four conditions.
- Recognition of the Academy under §3.3. It is not an instance and has applied for nothing.
- Any legal or tax question in the plan. Those belong to the partner's own counsel.

**Where the seed lives, and why it is not linked.** The seed is kept at `Development/Audio Arts Academy/` in the Institute's working documents. That folder also holds the partner's own manual and correspondence, which identify a private person, so it is referenced here and not published with this registry (§2.4). This entry is the public record of the act.

**Source of this entry.** The President's direction of 2026-11-07 that the seed be recorded as an act of the bootstrap period, and the seed's documents as they stood that day.

---

## Entry 6 — Secret scanning and push protection made the default for new NTARI-RAND repositories

| | |
|---|---|
| **Date of act** | 2026-11-11 |
| **Recorded** | 2026-11-11 |
| **Type** | Bootstrap act — a standing security default for the Institute's code organization on GitHub (NTARI-RAND) |
| **Authority** | §16.1 (founder board exercising the powers of the membership); recorded under §9.5 |
| **Decided by** | The President (Jodson Graves), for the founder board |
| **Status** | Valid; open to the membership under §2.3. Point 2 was carried out and verified on 2026-11-11. **Point 1 was not yet in effect when this entry was recorded** (see below). |

**What was decided.**

1. Every new public repository created in NTARI-RAND starts with two GitHub protections switched on. *Secret scanning* watches the repository for credentials such as API keys and passwords. *Push protection* refuses a push that contains a recognized credential, before it becomes public.
2. The same two protections were switched on for the nine public NTARI-RAND repositories that lacked them: Beacon, GovOS, Policies, Route, covenant-rand, economy-information-rand, governance-rand, record-rand and substrate-rand. Each had been created after the protections were enabled organization-wide on 2026-08-11. With this, every public, non-archived repository in NTARI-RAND and on the Institute's own GitHub account has both protections on.
3. The default covers only these two protections. GitHub's broader "recommended" configuration was deliberately not adopted as the default, because it would also switch on automated code scanning (CodeQL default setup), Dependabot alerts and private vulnerability reporting for every new repository. Those remain decisions for each repository. Automated code scanning in particular has conflicted with repositories that run their own scanning workflow.

**Why.** The Institute's full-history secret scan of 2026-11-11 found no live credential. (Its report is internal, because it lists where old, dead credentials sit.) It did find these nine public repositories unprotected, because the organization switched nothing on for new repositories, so each new repository started unprotected until someone noticed. A default closes that gap at its source. Credentials pushed to a public repository are exposed the moment they land, and removing them later does not undo the exposure.

**Why point 1 was not yet in effect.** Changing an organization's defaults needs an owner credential with GitHub's `admin:org` permission. The working session that carried out point 2 held a credential without that permission, so its attempt to create the default was refused and nothing was changed. Point 1 takes effect when an organization owner applies it, either with that permission or through the organization's Code security settings. A later entry will annotate this one with the date it took effect.

**What this act did not decide.**

- Private repositories. Secret scanning on private repositories needs GitHub's paid Advanced Security, so the seven private repositories (four on the Institute's account, three in Q-Zoo) remain covered only by the Institute's own periodic scans.
- The Institute's own GitHub account (NetworkTheoryAppliedResearchInstitute). It is a personal account, not an organization, and has no new-repository defaults to set.
- Clean-up of old, dead credentials that still sit on stale branches and pull-request references, and any purge of repository history. The 2026-08-11 decision to skip a history purge stands. The scan report lists the optional branch clean-up.

**Source of this entry.** The President's directions of 2026-11-11 in a working session: to switch the protections on for the nine repositories, to make them the default for new ones, and to record that default as a bootstrap act. Also the scan report of the same day.

---

## Entry 7 — Annotation of Entry 6: the new-repository default took effect

| | |
|---|---|
| **Date of act** | 2026-11-11, 13:45 UTC |
| **Recorded** | 2026-11-11 |
| **Type** | Annotation of Entry 6 (§2.5: corrected by a later entry, not by rewriting) |
| **Authority** | The act recorded in Entry 6; recorded under §9.5 |
| **Status** | Entry 6, point 1 is in effect from 2026-11-11, 13:45 UTC |

**What happened.** An organization owner granted the working session the `admin:org` permission. The session then created an NTARI-RAND code security configuration named "NTARI secret protection" (GitHub configuration 294095) and set it as the default for every new public repository. Verified the same minute:
- Secret scanning: on.
- Push protection: on.
- Automated code scanning, Dependabot alerts, Dependabot security updates, validity checks and private vulnerability reporting: off. This matches Entry 6's point 3.

**One addition Entry 6 did not name.** GitHub switches on the *dependency graph* in every configuration. It lists the packages a repository depends on and changes nothing in the repository itself. It is free on public repositories, and most existing NTARI-RAND repositories already have it.

**What did not change.** Existing repositories are not attached to the configuration and keep their own settings. The nine repositories switched on under Entry 6, point 2 remain on. GitHub now marks the configuration as using its "Secret Protection" product. For public repositories this carries no charge.

---

## Entry 8 — LBTAS reading: page the volume, never the harm

| | |
|---|---|
| **Date of act** | 2026-11-12 |
| **Recorded** | 2026-11-12 |
| **Type** | Bootstrap act — a reading of the LBTAS specification by the office that oversees the LBTAS API. It is not an amendment. |
| **Authority** | §8.2 (the office of the President "directs research and development (RAND) on the Covenant Layer protocol, oversees the LBTAS API serving compliant covenant assessments to the network"). §16.1, because no Covenant Federation has yet elected the office. Recorded under §9.5. |
| **Decided by** | The President (Jodson Graves) |
| **Raised by** | [NTARI-RAND/Leveson-Based-Trade-Assessment-Scale#17](https://github.com/NTARI-RAND/Leveson-Based-Trade-Assessment-Scale/pull/17), an outside volunteer contributor's change that lets clients read a party's rating history in pages |
| **Status** | Valid; open to the membership under §2.3. The required changes were posted to that pull request on 2026-11-12. |

**The question.** The LBTAS specification says a read computes the active distribution "while still surfacing every dismissed event with its dismissing party and reason" (SPEC §6). It also says "A front end MAY forgive harm; it MUST NOT be able to hide it" (SPEC §4). Can a history read be split into pages, where page 1 carries only some of the records and the rest arrive by following a bookmark (a "cursor")?

**What was ruled.** Paging is allowed for volume and never for harm. Every response, whether paged or not, must carry:

1. every −1 rating, active or dismissed, named by the exchange it belongs to;
2. every dismissed event, at any level, with who dismissed it, why, and when;
3. the full active distribution, and the dismissed events counted separately at each of the six levels, so that no single pooled figure stands for dismissals.

Ordinary ratings and the full text of −1 comments may be paged behind a cursor. A front end must not present one page as a party's whole history.

**Why.**
- In SPEC §6, "a read" means each response, so each page must itself surface every dismissed event. A count alone names nobody.
- Under SPEC §4, a front end cannot be "able to hide" harm only if the data needed to show all of it arrives with every page. History is returned oldest first. Without this rule, an operator that showed page 1 and never followed the cursor would show a −1 count while leaving out the recent ratings behind it.
- The bylaws ask the same of every conformant implementation. §9.10(b): "Harm is surfaced and never diluted, and every exchange that received one must be named." §9.11: "No column is pooled with another."

**Why this is a reading, not an amendment.** No rating rule changes. What counts as active, the six-level distribution, and the effect of a dismissal are all unchanged. The ruling decides only what a read must carry. That is why the office of §8.2 could decide it, and why no vote of the delegates under §9.2 was needed.

**How it was reached.** Three independent reviews of the pull request's code took three angles: a strict reading of the specification's text, an adversarial test of how an operator could misuse paging, and a check against the official document's lines 6, 7 and 8 and bylaws §9.10–§9.11. All three concluded that paging can conform, but only on these conditions. No code was run in reaching the ruling.

**What this act did not decide.**
- The older tension between §9.11, whose chart tallies "every rating that party has ever received", and SPEC §6, whose active distribution excludes dismissed ratings. The separate per-level dismissed counts required above let a front end show both, but which one the chart must show is left open.
- The order of history. Oldest-first may stay, because the ruling makes harm visible whatever the order.
- The LBTAS repository's description of itself as "a leaf library" in CONFORMANCE.md, which has been out of date since its API was added. That is left for a separate maintainer change.

---

## Entry 9 — AGPL-3.0 for all of the Institute's work, documents and code alike

| | |
|---|---|
| **Date of act** | 2026-11-13 |
| **Recorded** | 2026-11-13 |
| **Type** | Board act amending a Board policy: P2-004 *Licensing and Enforcement Strategy*, Part 2. Taken during bootstrap. |
| **Authority** | P2-004 §2.1 (software is AGPL-3 "unless a Board resolution says otherwise") and §2.2–§2.3, a policy of the Board; the founder board acting as the Board, with §16.1 for the bootstrap period. Recorded under §9.5. |
| **Decided by** | The President (Jodson Graves), for the founder board |
| **Raised by** | [NTARI-RAND/governance-rand#4](https://github.com/NTARI-RAND/governance-rand/pull/4), research that recommended CC BY-SA 4.0 for documents. This act decides otherwise. |
| **Status** | Valid; open to the membership under §2.3. The relicensing of the Institute's repositories under point 4 is being carried out from 2026-11-13. |

**What was decided.**

1. Every work the Institute publishes is licensed under the GNU Affero General Public License, version 3 (AGPL-3.0): software, and documents alike. Documents include the bylaws, policies, research, technical and educational material, website text, translations and data. This holds until a stronger copyleft appears.
2. P2-004 Part 2 is amended to match. Its §2.3 assignments of Creative Commons Attribution-ShareAlike 4.0 (CC BY-SA 4.0) to technical documentation and educational content, and Creative Commons Attribution 4.0 (CC BY 4.0) to policy documents, are withdrawn. Its §2.2 criteria for licensing software on other terms are withdrawn too.
3. The change looks forward only. No act may impair a license already granted (§13.2). Every version already published under CC BY-SA 4.0, CC BY 4.0 or GPL-3.0 stays available under that license as well.
4. The Institute's repositories are brought into line. Their LICENSE files, notices and descriptions are changed to AGPL-3.0 wherever the Institute holds the copyright.

**Why AGPL for documents, against the research's recommendation.** The President's direction is one copyleft for everything the Institute makes, the strongest available, with no boundary between code and prose to police. AGPL treats any copyrightable work as "the Program" (§0) and the editable file as its source (§1). So a Markdown document under AGPL carries a duty to provide its editable source with every rendered or printed copy, which CC BY-SA does not require. The costs that governance-rand#4 sets out are accepted:
- Each copy must carry the full license text, not only a link (AGPL §4).
- AGPL does not itself bar DRM-locked copies.
- AGPL text cannot be imported into CC BY-SA commons such as Wikipedia.
- CC BY-SA images cannot be placed in AGPL documents.

**What this act did not decide.**

- **The JFA official document.** Its footer licenses the specification under CC BY-SA 4.0 (janus-facing-architecture.md, line 168). It is unchanged by this act. Changing it is an amendment of the official document under §9.2, and the conformance suite checks the licensing statement. It needs a separate act.
- **"Or any later version" or "only".** Notices written under this act name version 3 only. The Institute can later widen its own works to "or any later version", but cannot narrow a grant once made. The choice stays open, as governance-rand#4 asks.
- **Work others contributed.** It keeps the license it came in under unless its author agrees otherwise. The only such text in a repository being relicensed is the Phase 1 Conformance Report in governance-rand (governance-rand#2, GPL-3.0). It stays GPL-3.0. AGPL-3.0 §13 lets the two be combined.
- **P2-004 Part 3.** The contributor agreement and copyright assignment are not touched by this act; governance-rand#4 proposes their correction.

**Source of this entry.** The President's directions of 2026-11-13 in a working session: "we want to be AGPL-3 across the board until a stronger version of copyleft appears", and, after reading the research, "AGPL-3 for all docs and code. Make that real please."

---

## Deliberately not entered

Recorded so the gaps are visible rather than silent, per the discipline of §2.5.

- **Revisions of the official document before 2026-08-31** — the 2026-08-24 rebuild, the 2026-08-27 tightening to architecture-only, and the same-day retirements of `GOV-delegates`, `GOV-reopen`, `EI-operator-economy` and `EI-hybrid`. These predate the adoption of the bylaws and therefore predate the §9.5 duty. Entering them now would be historical reconstruction asserted as a register of acts, which is a different thing from a register. They are documented in [the concept triage record](https://github.com/NTARI-RAND/Janus/blob/main/jfa-concept-triage-2026-08-24.md) and in the suite's own lineage notes, and a reader looking for that history should go there.
- **The 2026-08-31 revision of L10** — the change from "completed regulatory review" to published local authorizations, with the null-jurisdiction case added. This is a registry change of exactly the kind §9.16 now covers, and it fell on the same date as the adoption of the bylaws. Whether it preceded or followed adoption is not determinable from the corpus, so whether the §9.5 duty had attached is genuinely unclear. It is flagged here for the Secretary to enter retrospectively or to place with the pre-adoption revisions above, and is left undecided rather than resolved by assumption.

---

*Network Theory Applied Research Institute, Inc. — 501(c)(3) — EIN 92-3047136 — Louisville, Kentucky*

*Licensed under the GNU Affero General Public License, version 3 only (AGPL-3.0-only), under Entry 9. The full text is in this repository's [LICENSE](LICENSE) file. This Markdown file is the registry's source.*
