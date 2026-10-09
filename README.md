# abstract-translator

An opencode / Claude-compatible agent skill that translates Chinese academic abstracts into publication-ready English for SCIE journals, with a focus on veterinary microbiology and related life sciences.

将中文学术摘要翻译成可直接投稿的 SCIE 期刊英文摘要的 Agent Skill（兽医微生物学 / 病毒学 / 细菌学 / 寄生虫学 / 传染病 / 免疫学 / 分子生物学方向）。

## What it does

- Translates the Chinese abstract into natural, idiomatic academic English (not literal translation)
- Enforces the **B-P-M-F-I** abstract structure: Background, Purpose, Methods, Findings, Implications
- Applies field-correct microbial nomenclature (ICTV, strain/isolate/genotype distinctions)
- Runs a mandatory 7-step workflow and 6-dimension quality check internally
- Strict anti-fabrication rules: never invents results, ethics approvals, numbers, or citations
- Optional title / keywords translation; optional `[Author query]` line only when the source has a blocking issue
- Default: American English, max 250 words, overridable by target journal requirements

## Install

### opencode

Copy the folder into your skills directory:

```bash
# Global (all projects)
cp -r abstract-translator ~/.config/opencode/skills/

# Or project-local
cp -r abstract-translator your-project/.opencode/skills/
```

Or register this repository as a skills path in `opencode.json`:

```json
{
  "skills": {
    "paths": ["/path/to/this/repo"]
  }
}
```

Restart opencode after installing.

### Claude Code / Claude-compatible

```bash
cp -r abstract-translator ~/.claude/skills/
```

## Usage

Just ask in chat:

> 帮我翻译这篇摘要：（贴入中文摘要）

Optional inputs you can provide:

- Target journal name
- Journal abstract requirements (word limit, structured/unstructured, British English)
- Chinese title and keywords

## Files

```
abstract-translator/
└── SKILL.md    # the skill definition (frontmatter + translation specification)
README.md
LICENSE
```

## License

MIT
