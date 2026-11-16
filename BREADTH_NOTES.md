# Build notes - Biomedical NLP & Literature Mining

Repo2RLEnv pr_diff (v0.9.6), Harbor-format output. Domain: biomedical-nlp.

## Funnel

| Stage | Count |
|---|---|
| Domain candidates (deduped) | 226 |
| After active+star+noise filter | 64 |
| Final target list (cap unlimited) | 64 |
| Repos with >=1 task | 1 |
| Repos with 0 tasks | 52 |
| Total tasks (unlimited (no per-repo cap)) | 13 |

## Generation

- Shared task bank: each repo generated once (pr_diff, limit=3,
  max_files_per_pr=15, min_loc_changed=2), 4-way concurrency,
  rate-limit-aware with .done checkpoint resume.
- Per-domain consolidation: rank by reward_calibration.loc_changed desc,
  keep ALL qualifying tasks (no per-repo cap). Zero-yield repos are NOT fabricated.
- Overlap with the 3 published cancer editions is allowed (user decision);
  domains are independent selections, not a partition of one repo set.

## Zero-yield repos (informational, 52)

- Anil-matcha/Open-Generative-AI
- spmallick/learnopencv
- architecture-decision-record/architecture-decision-record
- flairNLP/flair
- Future-House/paper-qa
- stanfordnlp/stanza
- jtleek/datasharing
- TideDra/zotero-arxiv-daily
- dnhkng/GLaDOS
- km1994/nlp_paper_study
- songguoxs/gpt4o-image-prompts
- DSXiangLi/DecryptPrompt
- MIT-LCP/mimic-code
- wuyoscar/Internal-Safety-Collapse
- LichAmnesia/GPT-Prompt-Hub
- beita6969/ScienceClaw
- medspacy/medspacy
- AgentTeam-TaichuAI/ScienceClaw
- genomoncology/biomcp
- ncbi-nlp/BioSentVec
- ncbi-nlp/bluebert
- jannisborn/paperscraper
- abachaa/MedQuAD
- naivenaive/EasyPubMed
- jonatasgrosman/findpapers
- wp-a/nature-academic-search
- Aperivue/medsci-skills
- CYC2002tommy/Deep-Research-Agent
- duyunzhoudyz/dyz-med-paper-skills
- mkucej/i-librarian-free
- anoopkcn/obsidian-reference-map
- dmis-lab/BERN2
- vanthree31/PaperLens
- Dianel555/paper-search-mcp-nodejs
- BIDS-Xu-Lab/Me-LLaMA
- cyanheads/pubmed-mcp-server
- AstraBert/PapersChat
- kermitt2/biblio-glutton
- JamesANZ/medical-mcp
- lisc-tools/lisc
- drpwchen/paper-radar
- justinphan3110/SciFive
- mauro-nievoff/MultiCaRe_Dataset
- AstraZeneca/KAZU
- krassowski/easy-entrez
- ssinder/bioinformatics-agent-skills
- FareedKhan-dev/agentic-knowledge-graph
- htlin222/robust-lit-review
- WGLab/Bioformer
- hiddenblue/Pubmedsoso
- ddomingof/PubMed2PDF
- JetBrains-Research/pubtrends

## Caveats

- Static validation only; real grading needs an LLM judge key + Docker.
- inline_dockerfile mode skips image build (no Docker daemon needed to publish).
- Provider secrets in upstream diffs were redacted before public release.
