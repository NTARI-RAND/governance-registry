# NTARI Governance Registry

The public, append-only governance registry required by §9.5 of the [bylaws](https://github.com/NTARI-RAND/bylaws/blob/main/P1-001_Bylaws_v1.0.md) of the Network Theory Applied Research Institute. The registry is one file: [GOVERNANCE-REGISTRY.md](GOVERNANCE-REGISTRY.md).

It records:
- recognitions and lapses of membership;
- the publications of Article XI;
- expulsions, readmissions and re-entries under Article XII;
- each amendment of the official document ([NTARI-RAND/Janus](https://github.com/NTARI-RAND/Janus)) and of the bylaws ([NTARI-RAND/bylaws](https://github.com/NTARI-RAND/bylaws)).

While the founder board exercises the powers of the membership (§16.1), each act it takes under that authority is recorded here as a *bootstrap act*.

## How the registry is kept

- **Append-only (§2.5).** New entries go at the end. A mistake is corrected by a later entry that annotates the earlier one. No entry is deleted or rewritten.
- **Keeper.** The Secretary (§9.5). During bootstrap the founder board holds the function (§16.1).
- **Privacy floor (§2.4).** Parties are identified by role and by reference, never by personal information beyond what the proceeding requires.
- **By pull request.** Every commit carries a Developer Certificate of Origin sign-off (`git commit -s`), checked with no bypass.
- **Nothing is closed for good (§2.3).** Every recorded act stays open: any member may bring a decided matter back before the body under §6.7.

## License

GNU Affero General Public License, version 3 only (AGPL-3.0-only), under Entry 9 of the registry. The full text is in [LICENSE](LICENSE). The Markdown file is the registry's source: whoever passes on a rendered or printed copy must also make that source available, as AGPL §6 requires.
