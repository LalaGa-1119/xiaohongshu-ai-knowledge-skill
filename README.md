# Xiaohongshu AI Knowledge Carousel Skill

A Codex Skill for AI knowledge creators on Xiaohongshu. It turns keywords, articles, screenshots, or scattered notes into a focused topic, verifies concepts, plans a carousel script, guides consistent image generation, evaluates every page, and performs a final pre-publish check.

It is not a simple “summarize this into a few slides” tool. It helps answer three harder questions: **What is worth explaining, how can a beginner understand it, and how can the creator repeatedly produce a reliable final post?**

## Complete Example

The first full example is an eight-page Xiaohongshu carousel explaining what a Skill is, why it matters, and how to get started.

![Eight-page Skill explainer carousel](xiaohongshu-ai-knowledge-post/assets/case-skill-carousel.png)

## Capabilities

- **Topic analysis:** extracts the strongest single post from long text, multiple files, screenshots, or keywords instead of blindly summarizing everything.
- **Concept verification:** checks official documentation, standards, and primary research to confirm what something is, why it matters, and how it is used.
- **Carousel planning:** confirms the learning goal and page count before outlining the cover, pain point, definition, mechanism, example, and conclusion.
- **Page scripting:** specifies copy, scene, character action, expression, composition, and image-generation instructions for every page.
- **Visual consistency:** maintains a 3:4 hand-drawn layout, typography hierarchy, color palette, and consistent Lala-and-cat character system.
- **Image evaluation:** checks copy, concepts, characters, anatomy, object direction, layout, and publishing safety, then uses real revision feedback for regression tests.
- **Publish preparation:** creates one recommended title, alternatives, a description under 200 Chinese characters, topic suggestions, and an AI-content disclosure reminder.
- **Editor checks:** detects failed image loading, incorrect order, plain hashtag text that was not converted into a real topic, and other pre-publish issues.

## Suitable Inputs

| Input | Example | What the Skill Does |
| --- | --- | --- |
| AI keyword | Agent, RAG, AIGC, Skill | Verifies the meaning, then chooses a beginner-friendly angle |
| Long article or course notes | Chapters, lecture notes, transcript | Decides what belongs in this post and what should become a follow-up |
| Screenshot or file | Product page, report, class material | Extracts key points, verifies facts, and converts them into a carousel script |
| Scattered thoughts | Ideas, sentences, chat excerpts | Fills logical gaps and forms one clear learning promise |
| Generated images | Cover, inner pages, character art | Uses the evaluation set to find problems and request precise edits |
| Publishing draft | Title, copy, images, and tags | Checks both the finished content and the platform editor state |

This Skill is not designed for bulk reposting, chasing trends without verification, copying another creator's watermark or character, or using a story to hide conceptual errors.

## Workflow

1. **Read the source:** identify the subject, evidence, audience, and ambiguity.
2. **Analyze the topic:** evaluate beginner relevance, visual potential, practical value, confidence, and differentiation.
3. **Verify facts:** use current primary sources; ask the user when a term has multiple meanings.
4. **Confirm the plan:** present the angle, reader outcome, page count, and job of every page before generating images.
5. **Write the script:** prefer dialogue, action, comparison, and causality so that the story serves the concept.
6. **Generate images:** create or revise one page at a time while preserving the visual and character anchors.
7. **Evaluate every page:** accept an image only after it passes all hard gates and meets the quality threshold.
8. **Prepare publishing copy:** provide titles, body copy, topics, and an AI-content disclosure reminder.
9. **Run the final check:** verify image loading, order, official topics, preview, and visibility; request confirmation before the final publish action.

Detailed rules:

- [Content workflow](xiaohongshu-ai-knowledge-post/references/content-workflow.md)
- [Visual system](xiaohongshu-ai-knowledge-post/references/visual-system.md)
- [Image evaluation set](xiaohongshu-ai-knowledge-post/references/eval-set.md)
- [Publishing checklist](xiaohongshu-ai-knowledge-post/references/publish-checklist.md)

## Installation

### Option 1: Clone the Repository

```bash
git clone https://github.com/LalaGa-1119/xiaohongshu-ai-knowledge-skill.git
```

Copy the skill directory into the Codex skills directory:

```bash
cp -R xiaohongshu-ai-knowledge-skill/xiaohongshu-ai-knowledge-post ~/.codex/skills/
```

Restart Codex or open a new task so the Skill can be discovered.

### Option 2: Install Only the Skill

Keep the complete `xiaohongshu-ai-knowledge-post/` directory. Do not copy `SKILL.md` by itself because the workflow depends on the visual specification, evaluation set, and publishing checklist under `references/`.

## Usage

Explicitly invoke the Skill and provide your source material. Ask it to analyze the topic before generating images:

```text
Use $xiaohongshu-ai-knowledge-post to turn these Agent course notes into a beginner-friendly Xiaohongshu knowledge carousel. Analyze the topic before generating images.
```

You can also provide mixed inputs:

```text
Use $xiaohongshu-ai-knowledge-post. I have an article, three screenshots, and a few personal notes. Choose the strongest post and recommend a page count.
```

To evaluate finished images:

```text
Use $xiaohongshu-ai-knowledge-post to evaluate these six images with the evaluation set. Mark each page as accepted or revise, and list the required changes.
```

To prepare publishing copy:

```text
Use $xiaohongshu-ai-knowledge-post to provide one recommended title, two alternatives, body copy under 200 Chinese characters, and suitable topics.
```

The Skill proposes a topic and page plan first. It begins page-by-page image generation only after the concept, page count, and visual direction are clear.

## Visual System

- **Canvas:** 3:4 portrait on a warm off-white paper background.
- **Linework:** deep navy or black hand-drawn ink lines with slight handmade irregularity while remaining legible.
- **Accent colors:** navy, sky blue, and orange; avoid unnecessary colors.
- **Typography:** the main cover term is largest; inner pages use a clear title–point–supporting-detail hierarchy.
- **Layout:** explanatory text sits at the top or bottom, leaving the center for characters, objects, or diagrams. Speech bubbles are used only for actual speech or thought.
- **Lala:** high ponytail, off-white T-shirt, loose dark trousers, blue-and-white sneakers, and an orange hair clip; lively without being exaggerated.
- **Cat:** small and slender, one upright ear and one folded ear, an orange tag, and an arrow-shaped tail tip; anatomy and proportions must be correct.
- **Continuity:** books, cards, tags, and other objects keep a sensible direction and state across panels.

Visual consistency does not mean repeating the same composition. Characters, colors, and texture should remain stable while scenes and character count follow the content.

## Project Structure

```text
xiaohongshu-ai-knowledge-skill/
├── README.md
├── LICENSE
└── xiaohongshu-ai-knowledge-post/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    ├── assets/
    │   └── case-skill-carousel.png
    └── references/
        ├── content-workflow.md
        ├── eval-set.md
        ├── publish-checklist.md
        └── visual-system.md
```

`SKILL.md` contains only the core workflow. Detailed rules are loaded from `references/` as needed to reduce irrelevant context.

## Quality Gates

Every page must pass seven hard gates:

1. Copy is complete, accurate, and legible; every speech bubble belongs to the correct character.
2. The concept is correct and is not distorted by an analogy.
3. Lala and the cat retain their fixed character traits.
4. There are no extra paws, fingers, limbs, faces, or tails.
5. Books, tags, cards, and other objects have a sensible direction and state.
6. The page uses a clear 3:4 layout and reading order.
7. It does not copy a reference creator's watermark, impersonate another person, or misuse third-party marks.

After passing the hard gates, each page is scored for its hook, single-page focus, beginner clarity, narrative purpose, hierarchy, spacing, hand-drawn consistency, expression, character proportions, palette, and copy-image alignment.

Before publishing, confirm that:

- image count, order, and cover are correct;
- no image becomes blank after draft recovery or refresh;
- tags were added through the platform topic picker rather than left as plain hashtag text;
- “AI-generated content” is selected when applicable;
- the user has approved the final publish action;
- success is verified on the result page or in the post management list.

## License

The code and documentation are released under the [MIT License](LICENSE). You may use, copy, modify, merge, publish, and distribute them while preserving the copyright and license notice.

Example images demonstrate this Skill's workflow. The open-source license does not grant permission to copy another creator's watermark, character design, or protected work. When using references, extract abstract composition, color, and storytelling principles and build original character assets.
