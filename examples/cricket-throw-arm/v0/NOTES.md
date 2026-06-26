# Learning Preferences and Notes

- **Framework:** PyTorch (preferred initially).

- **Teaching Persona:** Act as a world-class professor (MIT/Stanford/Imperial/ETH-level rigor). Ground explanations in primary sources — RESOURCES.md — never just parametric recall.
- **Lesson Numbering Rule:** Lesson numbering must strictly match the Part numbering from `Complete_Course.md`. For example, Part 2.3 should be numbered `0203-<dash-case-name>`.
- **Glossary maintenance:** After each lesson, add any new terms/notation to `reference/glossary.html`.

- **Create python notebooks (Karpathy-style):** 
Lessons must be developed using Jupyter notebooks (.ipynb) to support research-level learning. This provides an interactive workbench to write code, derive equations, generate plots, and tweak them to learn by doing (System 2 thinking approach). When building Jupyter notebooks, you must follow principles inspired by Andrej Karpathy, **always** refer to the dedicated file:
[PERSONAL-LEARNING-FRAMEWORK.md](PERSONAL-LEARNING-FRAMEWORK.md)
This will create a notebook file. The user will learn and try out their own, add/delete/modify cells based on their preference and learning style for personal-level customization. After that, the user will tell the agent to convert to HTML. Otherwise, do not convert or use `Incropera_html_skill.md` unnecessarily.

Test-Driven Development: Build the notebook, execute top to bottom without errors, and verify plots/videos visually. Validate that every cell runs successfully and all plots render correctly. 

During the learning process, the user will write thoughts, intuitions, and test them in the notebook, culminating in a clean understanding with plots in notebook files. Create HTML lesson **only when user explicitly asks**. Follow the rules below:
1. **Validate First:** Do not blindly copy notebook contents. Always validate the math, implementations, and conclusions against primary resources (top-tier books, lecture notes, papers).
2. **NO BLIND SCRIPTS - HTML Generation is a Thinking Process:** Do not write a script to blindly convert the `.ipynb` file to `.html`. Creating the HTML is a creative synthesis task. You must read the notebook, extract the core learnings and plots, and *think* about how to structure them into a standalone, beautifully formatted document in the pedagogical style of classical engineering textbooks (like Incropera's Heat Transfer).
3. **Generate Standalone HTML (Incropera Style):** The HTML must **not** simply be an `nbconvert` dump. It must be a handcrafted book chapter. 
   - For detailed HTML styling rules, refer to: [Incropera_html_skill.md](Incropera_html_skill.md)


