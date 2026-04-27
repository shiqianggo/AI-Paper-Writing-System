
# 人工编写提示词

```
You are writing the Results section of an SCI manuscript.

Write the Results strictly based on the provided figures, tables, legends, methods, supplementary materials, and validated results.  
Do not invent numbers, references, mechanisms, or interpretations beyond the evidence.

Requirements:

- Prioritize figure/table evidence.
- Use Methods only to clarify experimental design or metric definitions when needed.
- Keep the writing objective, concise, and academic.
- Do not mix Discussion-style interpretation into Results.
- If exact numbers are missing, use *** or [Data Required].
- If evidence is insufficient for a strong claim, use conservative wording.

Output requirements:

1. Write in formal SCI English.
2. Organize the Results according to the figure/result logic.
3. Use subheadings if appropriate.
4. Keep only evidence-supported statements.
5. Do not add references.

我们整个结果分几个部分，整个的结果对分三个部分，然后第一个部分是讲表型，包括figure 1和Figure S1的内容；第二部分讲转录组和代谢组的结果，包括Figure2和Figure S2的内容，第三部分讲SNP和表型组学整合的结果，包括Figure3 和Figure S3的内容。请根据输入的三个word文件，对这部分内容开展学术论文的写作。如果图表中没有的相关信息，请到method文件中查阅，并总结，以简练的语言归纳到结果的表述中，作为衔接引出后面的结果。 结果的第一部分： 应该先讲在章江口这个区域，我们利用卫星的数据，根据它出现的时间定位了斑块并进行了采样，然后对这些样品进行了表型测量，请提取和总结methods文件中的信息，并引用figure 1和Figure S1。再仔细读取Figure1和Figure S1的中的信息，以及对应的图注。请从图b-d逐一描述表型的结果，以及FigureS1中表型的结果，说明这些表型在不同年份间是否有差异。最后总结一下，我们根据时间根据斑块出现时间采样，测量的表型结果，在不同年间的总体变化规律，对吧？这是第一段的内容。 结果第二部分 第二部分第一段：这一段我们主要介绍采样和组学数据，包括基因组的注释等。为了深入研究这些斑块间的差异，我们引入了代谢组学和转录组学的测量方式，然后我们以之前发表的基因组为模板，进行了新的注释，这里请添加一下基因组注释相关的信息，如注释的准确度，共注释到多少基因，从method文件中提取这个信息，如果没有具体数字请留出***，方便我们后续填充。 第二部分第二段：我们进行了代谢的采样，采集了多少个样品，转录组的数据质量如何，得到多少基因表达，请根据method填充细节。我们将转录组的结果进行了聚类分析，阅读Figure 2a这是转录组PCA，请总结一下这张图的发现整体转录组格局。我们通过NFUZZ对其进行了最小距离的判定，判定的结果分成四种表达趋势（Figure S2a，）针对这四种表达趋势中高置信值得到的基因，分别为12026, 10033, 5453, 10196（Figure S2c），进行了GO富集分析，四类表达趋势的GO富集结果分别对应Figure 2c,2d,2e,2f。请仔细阅读这四张小图，梳理其中的GO通路，并总结。最后，用一句话总结，总结转录组的发现，从趋势和功能两个角度总结。 第二部分第三段：下一段就是要讲关于代谢组的研究。在代谢组当中，我们一共通过什么样的分析方法，得到了多少个代谢物，进行了pca的聚类，PCA结果为Figure2b，请描述Figure2b，总结整体格局。我们也针对代谢组进行了与转录组类似的最小距离判定，得到了四类代谢产物，结果为FigureS2b，以及Figure S2d，请总结图中信息。针对这四类代谢产物，我们开展了KEGG聚类分析，KEGG的结果为Figure2g,请阅读这张图，总结每一年代谢产物的情况。最后，用一句话总结，总结代谢组的发现，从趋势和功能两个角度总结。 第三部分 第三部分第一自然段：我们介绍总体的遗传格局。我们首先计算了样本间的亲缘关系，如图Figure3a，请阅读这张图和图注，总结这张图的格局和结果。Figure 3b是我们通过Fst和Pi值的前5%的交集挑选出来的显著分化的SNP位点，形成的PCA分析结果，请描述这张图的结果。 第三部分第二自然段：为了探究不同年份定殖的斑块其生长和繁殖表型，是由哪些因素决定的，包括位置，遗传（基因组的SNP），转录和代谢。我们开展了贝叶斯层级模型分析，Baysian模型的performance评估的结果为Figure S3a和Figure S3b, 请阅读图注，以及图中的内容，总结performance评估的结果。Baysian模型分析的结果为Figure3c-g，首先结合图注，描述一下每张小图的内容。然后，根据图中箭头的方向，和统计量及其显著性，描述一下位置、基因组、转录和代谢等因素，如何直接和间接的影响生长和繁殖表型。最后，总结一下这段的内容。
```

# Gemini优化提示词

```
```text
You are helping optimize a manuscript-writing prompt for use with a large language model.

Your task is NOT to write the manuscript section itself.
Your task is to rewrite and improve the user's original prompt so that another model can better understand it and generate a stronger SCI-style section.

Please improve the prompt in the following ways:
1. Make the structure clearer
2. Make the section logic easier to follow
3. Make the evidence sources more explicit
4. Add boundary controls to prevent overinterpretation or hallucination
5. Keep the prompt concise but informative
6. Preserve the author's true scientific intent
7. Keep placeholders such as *** or [Data Required] when specific numbers are missing

Requirements:
- Do not write the manuscript section itself
- Do not add unsupported facts, references, or conclusions
- Do not change the author's intended section logic
- If the original prompt is too loose, reorganize it into a more structured writing instruction
- Make the final version more suitable for academic manuscript generation

Input:
Section: {section}
Topic: {topic}
Field: {field}
Study system: {study_system}
Research question: {research_question}
Core novelty: {core_novelty}

Original human-written prompt:
{raw_prompt}

Available materials:
- Figures and legends: {figures}
- Methods: {methods}
- Supplementary materials: {supplementary}
- Validated key results: {validated_results}
- Key numbers table: {key_numbers}
- Target journal style: {journal_style}

Output format:
### 1. Optimized prompt
### 2. Brief note on what was improved
```


# Gemini优化后提示词

```
You are an expert academic writer and researcher, tasked with writing the Results section of an SCI manuscript.

Your objective is to write a highly structured, objective, and professional Results section strictly based on the provided figures, tables, legends, methods, supplementary materials, and validated data.

# CORE DIRECTIVES & BOUNDARY CONTROLS
1. No Hallucination: Do not invent numbers, reference citations, biological mechanisms, or interpretations that are not explicitly present in the provided evidence.
2. Evidence First: Prioritize findings derived directly from Figures and Tables.
3. Methodological Context: Use the [Methods] file only to briefly introduce experimental designs, sampling strategies, or metric definitions as transitional sentences to contextualize the results.
4. Separation of Results and Discussion: Keep the writing objective. State *what* was found, not *what it implies*. Do not mix Discussion-style speculation into this section.
5. Missing Data Handling: If specific methodological numbers or precise values are not found in the provided texts, use `***` or `[Data Required]` as placeholders. Do not guess.
6. Tone: Use formal, concise SCI-standard English. Use conservative wording if the provided evidence is weak or borderline.

# SECTION WRITING LOGIC & STRUCTURE
Please organize the Results section into three main parts with appropriate subheadings based on the instructions below. 

## Part 1: Phenotypic Variations Across Colonization Years
- Paragraph 1: Start by briefly extracting information from the [Methods] file to introduce the study site (Zhangjiangkou area) and how satellite data was utilized to determine the timing of patch appearance for guided sampling. Summarize how phenotypic measurements were conducted. 
- Next, carefully examine **Fig 1b-d** and **Fig S1** (along with their legends) to describe the phenotypic results, specifically addressing whether there are significant phenotypic differences across different years. 
- Conclude this paragraph with a brief summary statement regarding the overall temporal patterns of phenotypic changes over time in these patches.

## Part 2: Transcriptomic and Metabolomic Dynamics
- Paragraph 1 (Omics Overview): Introduce the integration of transcriptomics and metabolomics to investigate differences among patches. Mention that a previously published genome was used as a template for new annotation. Extract specific figures regarding annotation accuracy and the total number of co-annotated genes from the [Methods] file (use `***` if unavailable).
- Paragraph 2 (Transcriptomics): Extract transcriptome sampling details, data quality, and the number of expressed genes from the [Methods] file. Describe the overall transcriptomic variation pattern based on the PCA (**Fig 2a**). Explain the four distinct expression trends identified via Mfuzz minimum distance classification (**Fig S2a**). explicitly state that the high-confidence genes for these four trends are 12026, 10033, 5453, and 10196, respectively (**Fig S2c**). Read **Fig 2c, 2d, 2e, 2f** to summarize the GO enrichment pathways for each of these four expression trends. Conclude with a single sentence summarizing the overall transcriptomic findings from both expression-trend and functional perspectives.
- Paragraph 3 (Metabolomics): Describe the overall metabolomic profile and PCA clustering (**Fig 2b**). Explain the minimum distance classification applied to metabolites, yielding four distinct metabolite groups (**Fig S2b, Fig S2d**). Describe the KEGG pathway enrichment analysis for these four groups across different years based on **Fig 2g**. Conclude with a single sentence summarizing the metabolomic findings from both trend and functional perspectives.

## Part 3: Genetic Architecture and Multi-omics Integration
- Paragraph 1 (Genetic Structure): Introduce the overall genetic landscape. Summarize the sample kinship patterns using **Fig 3a** and its legend. Describe the PCA results (**Fig 3b**) which were generated using significantly differentiated SNP loci (derived from the intersection of the top 5% Fst and Pi values).
- Paragraph 2 (Multi-omics Integration via Bayesian Modeling): Introduce the objective: exploring how location, genetics (SNPs), transcriptomics, and metabolomics determine the growth and reproductive phenotypes of patches colonized in different years. Detail the Bayesian hierarchical modeling approach. First, summarize the model's performance evaluations based on **Fig S3a** and **Fig S3b**. Then, thoroughly examine **Fig 3c-g**. Based on the directions of the arrows, statistical values, and significance levels in the network, explicitly describe how location, genome, transcriptome, and metabolome exert direct and indirect influences on growth and reproductive phenotypes. Conclude this paragraph with a concise summary of these integrative findings.

# INPUT MATERIALS
- Figures and legends: [Insert Content Here]
- Methods: [Insert Content Here]
- Supplementary materials: [Insert Content Here]

Please generate the Results section now.
```


---

- [[Prompt-写作提示词优化]]
- [[Prompt-Results写作]]