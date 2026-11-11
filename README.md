# EBMT 移植專科複習室

Buildless static site. Serve `dist/` with any static host. `dist/book.json` contains 94 chapters, Chinese exam summaries, original subsection bookmarks, extracted English text, and reference queries. Original chapter PDFs retain the original author and licensing notices.

Source: The EBMT Handbook (2024), edited by Anna Sureda, Selim Corbacioglu, Raffaella Greco, Nicolaus Kröger, Enric Carreras. DOI: https://doi.org/10.1007/978-3-031-44080-9. CC BY 4.0: https://creativecommons.org/licenses/by/4.0/ . Chinese summaries and self-assessment prompts are adaptations, not an official EBMT translation. Source authors are credited in each PDF and linked publisher chapter.

User progress, bookmarks, notes and quiz self-ratings use localStorage only. Backups are explicit JSON export/import. Citation extraction may omit or merge text; verify the PDF References. The original is the user's supplied 840-page PDF; use actual PDF page numbers, not contents-page printed numbers.

Validation: JS syntax; programmatic rendering of 94 chapters in all 3 tabs, 7 comparisons, quiz, filters, escaping; all 94 PDF page counts and metadata bounds. Browser visual QA unavailable because the managed computer-use runtime tool is not installed.

## Paragraph translation — batch 1

`dist/translation.js` adds a separate full-text reading layer. `translations/index.json` explicitly records chapter 1 and chapter 6 as having body translations, and 92 chapters plus front matter as pending. Only the two completed chapter data files are published. The 125 aligned blocks include original-language bibliography entries; they are not 125 translated body paragraphs. Body text, figure captions/labels and chapter key points in this batch were translated by the assistant and checked against source text; no human specialist review is claimed. Original figures remain in the PDFs. An explicitly separated translator note addresses the source's reference to Wilcoxon signed-rank for independent-group survival comparisons.

The attempted whole-book Google Translate draft is not published. Service rate limiting and unreliable ordering of source columns prevented completing that draft. Cache/checkpoint files remain outside the site repository. No ongoing background translation is scheduled.

Validation: all original smoke checks; render both actual translation JSON files; verify 92 pending states, lazy-loaded route handling, chapter search, display modes, page links and escaping. Browser visual QA remains unavailable because the managed `cua_repl.js` tool is absent.

## Direct translation — chapters 90–94

The linked automation had been disabled before this historical batch. Published paragraph translations at that point covered chapters 1, 6 and 90–94 (7 of 94). The batch added 516 aligned blocks over 53 source PDF pages, including original-language reference entries. It is an AI translation of the chapter body, subsection text, tables, captions and original key points where present, with English technical terms and bibliography retained. Original figures and full layout remain in the PDFs. It has not had human specialist review.

The SCID genotype table was checked visually against the original columns. Cross-page paragraphs and figure/body interleaving were reconstructed explicitly. Table typography was normalized for dosages/superscripts, with source inconsistencies identified rather than silently corrected. Chapter 94 preserves the book's R2Pulm sentence but attaches a prominent separate correction linked to PMID 31553693 and DOI 10.1200/JCO.19.00915, whose abstract reports no clear BuMel advantage and more severe toxicity. Notes remain visible in the English-only mode as well.

The translation library derives completed/pending counts from the manifest. The global search also indexes the new Chinese full-text content. Existing chapters 1/6, user localStorage records, reference queries and original PDF assets were preserved.

Validation: JS syntax; all original application smoke checks; rendering all 7 actual translated chapters and 87 pending states; chapter/page/block bounds; explicit source-body coverage mappings; table genotype/dose values; citation/correction links; search, mode and HTML escaping checks. Browser visual QA was skipped because the Sites-managed `cua_repl.js` tool is absent; no substitute browser was installed.

## Hourly continuation — chapters 88–89

The user later re-enabled private, scheduled continuation and explicitly consented to sending chapter text to Google Translate. Published paragraph translations now cover chapters 1, 6 and 88–94 (9 of 94). This batch adds 81 bilingual blocks over 17 source PDF pages. Chapter bodies, subsection headings, transplant result tables, therapeutic algorithms, figure labels, key points and licensing text are included; English bibliography entries are retained. Google-assisted drafts were checked against the PDFs for two-column reading order, negation, numeric values, percentages, exponents and table row alignment. Garbled or omitted table values were manually reconstructed from the source before publication. The translations remain AI-generated and have not had human specialist review.

The manifest marks all other chapters and the front matter as pending. Existing notes, bookmarks, localStorage data and original PDF/page links are unchanged. Validation covers JSON schema and bounds, unique block IDs, source-page mapping, required numeric tokens, negation review, Traditional Chinese checks, rendering/search/display modes, escaping and the original application smoke tests.


The next published batch adds chapters 86–87: 197 bilingual blocks over 13 source PDF pages. Chapter 87 (mantle cell lymphoma) and chapter 86 (large B-cell lymphoma) retain subsection order, transplant result tables, the treatment algorithm and figure caption, key points, English references, and original PDF page links. Numeric values, negation, table rows, and Traditional Chinese terminology were checked against the source PDFs. The translation service began rate-limiting during chapter 85, so chapters 84–85 remain clearly pending and were not published from an incomplete cache. The translations remain AI-generated and have not had human specialist review.


## Hourly continuation — chapters 84–85

This batch adds chapters 84–85: 178 bilingual blocks over 12 source PDF pages. The indolent lymphoma and chronic lymphocytic leukemia chapters preserve subsection order, transplant outcome tables, key points, English references, licensing text and original PDF page links. Numeric values, percentages, confidence intervals, negation, cross-page sentence fragments and Traditional Chinese terminology were checked against the source. The translations remain AI-generated and have not had human specialist review.


## Direct AI translation — chapters 83 and 82 (2026-11-11)

The user authorized direct paragraph translation and optional use of the official Google Cloud Translation API. Direct AI translation is now the default; the scheduled task no longer waits for the unofficial Google endpoint. No Google Cloud credentials were configured in this environment and no Cloud API billing was enabled.

Added 74 bilingual blocks across 10 source PDF pages: chapter 83 (POEMS and monoclonal immunoglobulin deposition disease) and chapter 82 (systemic AL amyloidosis). Entire chapter bodies, diagnostic criteria, treatment tables, footnotes, figure captions and axis labels, key points and licensing text were translated directly. References remain English with Google/Scholar lookup links. All ten source pages were rendered and visually inspected; the POEMS prognosis/treatment boxes and AL key points were restored to their correct reading order. Numeric tokens, inequalities, units and superscripts, table row alignment and negation were checked. Source page links, notes/bookmarks and private access are preserved. These are AI translations, not specialist-reviewed clinical guidance.

## Direct AI translation — chapters 81 and 80 (2026-11-11)

Added 65 bilingual blocks across 24 source PDF pages: chapter 81 (multiple myeloma) and chapter 80 (sickle cell disease and thalassemia). The full chapter bodies, risk and response criteria, transplant and CAR-T study tables, disease-modifying therapy table, conditioning and survival figures, key points, licensing text, and English references are retained. References have Google and Scholar lookup links. All 24 pages were rendered and visually checked against the two-column originals; cross-page paragraphs interrupted by tables and figures were restored to their source reading order. Clinical numbers, percentages, inequalities, doses, units, superscripts and negation were reviewed. Existing notes, bookmarks, source-PDF links and owner-only access remain unchanged. The translations are AI-generated and have not received specialist review.

## Direct AI translation — chapters 79 and 78 (2026-11-11)

Added 63 aligned bilingual groups across 17 source PDF pages: chapter 79 (Fanconi anemia and other inherited bone marrow failure syndromes) and chapter 78 (severe aplastic anemia and paroxysmal nocturnal hemoglobinuria). The translated material retains all subsection content, author affiliations, transplant indications and outcomes, the Figure 79.1 survival/malignancy chart, the Figure 78.1 SAA treatment algorithm, the chapter 79 donor/source/dose/conditioning key-points table, chapter 78 key points, licensing text, and the complete English reference lists with Google and Scholar lookup links. Every page was rendered and checked against the original two-column PDF; cross-page continuations, negation, ages, survival values, doses, units, inequalities, exponents and trial identifiers were reviewed. Existing notes, bookmarks, source-PDF links and owner-only access remain unchanged. The translations are AI-generated and have not received specialist review.

## Direct AI translation — chapters 77 and 76 (2026-11-11)

Added 58 aligned bilingual groups across 21 source PDF pages: chapter 77 (myeloproliferative neoplasms, including myelofibrosis and CML) and chapter 76 (MDS/MPN overlap neoplasms). The full bodies, author affiliations, prognostic and transplant-risk scores, Figures 77.1–77.2, Tables 77.1–77.2, Tables 76.1–76.3, disease-stage and transplant-outcome values, molecular relapse thresholds, key points, licensing text, and complete English reference lists are retained with Google and Scholar lookup links. Every page was rendered and checked against the visual two-column source; page 703's extractor column inversion was manually restored. Percentages, ages, survival intervals, blood counts, doses, inequalities, exponents and mutation names were reviewed. Existing notes, bookmarks, source-PDF links and owner-only access remain unchanged. The translations are AI-generated and have not received specialist review.


## Direct AI translation — chapters 75 and 74 (2026-11-11)

Added 40 aligned bilingual groups across 14 source PDF pages: chapter 75 (allogeneic HCT in pediatric MDS/RCC and JMML) and chapter 74 (adult myelodysplastic neoplasms/syndromes). The full bodies, author affiliations, revised IPSS table, germline and JMML genetic-subtype table, conditioning and transplant-outcome evidence, both adult MDS treatment flow charts with translated labels, key points, licensing text, and complete English reference lists are retained with Google and Scholar lookup links. Every page was rendered and checked against the visual two-column source; the full-width tables and flow charts were reconstructed in semantic reading order. Percentages, blast thresholds, blood counts, ages, survival values, doses, inequalities, exponents, mutation names and negation were reviewed. Existing notes, bookmarks, source-PDF links and owner-only access remain unchanged. The translations are AI-generated and have not received specialist review.


## Direct AI translation — chapters 73 and 72 (2026-11-11)

Added 18 complete source-page bilingual groups across 18 PDF pages: chapter 73 (pediatric/adolescent ALL) and chapter 72 (adult ALL). Each page preserves all extracted English paragraphs alongside a complete Traditional Chinese paragraph translation, including HCT indication and donor tables, the FORUM outcome plot, adult treatment algorithm, donor-comparison figures, key-point outcome table, licensing text, and complete English reference lists with Google and Scholar lookup links. All 18 pages were rendered and visually checked against the two-column originals; full-width tables and figures, cross-page sentences, MRD thresholds, cell doses, radiation doses, percentages, survival estimates, inequalities, exponents and negation were reviewed. Existing notes, bookmarks, source-PDF links and owner-only access remain unchanged. The translations are AI-generated and have not received specialist review.

## Full-text revision of chapters 72–73 and direct AI translation of chapters 71–70 (2026-11-12)

Rebuilt chapters 72 and 73 from single-block-per-page summaries into paragraph-aligned full-text translations (chapter 72: 9 → 58 blocks across PDF pages 642–650; chapter 73: 9 → 77 blocks across PDF pages 651–659). De-interleaved two-column English extractions, restored full sentence-by-sentence Traditional Chinese translations without condensation, reproduced all rows/columns/footnotes of the CR1 allo-HCT prognostic factor table, Key Points outcome table, and Tables 73.1–73.4, detailed all flowchart pathways and survival plot risk tables (Figs. 72.1–72.3, Fig. 73.1), and separated all bibliography entries with individual Google and Scholar lookup links.

Added 241 aligned bilingual blocks across 31 source PDF pages for chapter 71 (pediatric AML, PDF pages 626–641, 121 blocks) and chapter 70 (adult AML and APL, PDF pages 611–625, 120 blocks). Full chapter bodies, subsection headings, ELN 2022 risk/MRD/treatment tables (Table 70.1), APL morphology/immunophenotype/genetic diagnosis and 16 RARA rearrangement tables, adult AML transplant algorithms and study tables (Tables 70.2–70.3), pediatric AML cytogenetic/molecular risk criteria, donor hierarchy and post-transplant targeted maintenance tables (Tables 71.1–71.2), key points, abbreviations, licensing text, and complete individual English reference entries with Google and Scholar links are included. Published full-text translations now cover 27 of 94 chapters (1, 6, 70–94; 244 pages, 1,773 aligned blocks).

## Direct AI translation — chapters 69–66 (2026-11-12)

Added 216 aligned bilingual blocks across 28 source PDF pages: chapter 69 (HCT in resource-constrained settings, PDF pages 602–610, 48 blocks), chapter 68 (HCT in elderly patients, PDF pages 596–601, 54 blocks), chapter 67 (overweight and obese patients, PDF pages 590–595, 47 blocks), and chapter 66 (extracorporeal photopheresis in adults and pediatrics, PDF pages 583–589, 67 blocks). Full chapter bodies, subsection headings, APBMT/LABMT activity figures (Fig. 69.1), HCT program development stages and essential medicines tables (Tables 69.1–69.2), elderly HCT outcome table and geriatric/frailty assessment criteria (Table 68.1), pharmacokinetic and weight-based dosing guidelines (Table 67.1), acute and chronic GVHD ECP clinical study tables (Tables 66.1–66.2), key points, licensing text, and complete individual English reference entries with Google and Scholar links are included. Published full-text translations now cover 31 of 94 chapters (1, 6, 66–94; 272 pages, 1,989 aligned blocks).
