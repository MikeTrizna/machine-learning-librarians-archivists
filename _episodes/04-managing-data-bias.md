---
title: "Understanding and managing bias"
teaching: 0
exercises: 0
questions:
- "What are common types of bias and their effect in machine learning?"
- "At what points can bias enter the machine learning pipeline?"
- "Can we manage bias? Some lessons from GLAM"
objectives:
- "Define bias in the context of machine learning"
- "Understand common types of bias and how and at what stages these may impact model predictions"
- "Consider a range of bias mitigation strategies available to GLAM staff"
keypoints:
- "Bias occurs when a dataset is not representative of the population, it is incomplete or skewed."
- "The presence of bias in the classifications and predictions of machine learning may have far reaching consequences for society, amplifying inequality and unfairness."
- "There are abundant opportunities for bias to enter ML systems at all stages of the pipeline including when datasets are constructed, when a models learning is refined and reinforced, and when predictions made by a model are interpreted by humans and applied to real world scenarios"
- "There are a range of strategies available today to help mitigate bias."  
---
FIXME

{% include links.md %}

## Bias in machine learning

Machine learning systems are reliant on the training data we feed them to learn and make predictions. A model learns by giving weight to what it thinks are the main points (also known as features), generalising from all the information it's been given, so that when it encounters new similar information, it can find a way to recognise and interpret it. Bias in this respect simply refers to the balance of weights learned by the model, resulting for instance in overemphasis of the wrong features. In fact a model may even find patterns correlating to features that have been actively omitted from the training data, inferring from other provided features. The problem comes, then, when that training data is incomplete, or skewed in any way either intentionally or unintentionally. The model will ultimately reflect this with consequences of varying degrees, from the morally neutral (poor model accuracy) to the profoundly injust as has happened with [predictive policing algorithms](https://www.propublica.org/article/machine-bias-risk-assessments-in-criminal-sentencing). 

One of the clearest illustrations of this is in the case of machine learning systems being relied upon as tools for courts to use in sentencing, aiming to predict the likelihood of defendents committing a future crime. Analysis by ProPublica in 2016 of one system used widely throughout the United States, Correctional Offender Management Profiling for Alternative Sanctions (COMPAS) tool, uncovered significant racial disparity between the system predictions for white and black defendants. The COMPAS tool assigns scores from 1 to 10 to a defendent based on 100 or so factors such as age, sex and criminal history although notably race has been excluded. While overall, "Northpointe’s assessment tool correctly predicts recidivism 61 percent of the time...blacks are almost twice as likely as whites to be labeled a higher risk but not actually re-offend. It makes the opposite mistake among whites: They are much more likely than blacks to be labeled lower risk but go on to commit other crimes. (Source: ProPublica analysis of data from Broward County, Fla.)". Interestingly, [a subsequent study](https://www.theatlantic.com/technology/archive/2018/01/equivant-compas-algorithm/550646/) has revealed that the COMPAS tool was actually no better at predicting crimes than random people on the internet. 

>“Although neural networks might be said to write their own programs, they do so towards goals set by humans, using data collected for human purposes. If the data is skewed, even by accident, the computers will amplify injustice.” — The Guardian

So while AI and machine learning (ML) systems may appear to us as objective and neutral, dealing solely in facts and numbers, free from troublesome human proclivities in their decision making, they are reliant on training data that can encode the unfairness, inequities, stereotypes and [cognitive biases](https://en.wikipedia.org/wiki/List_of_cognitive_biases) of the real world. 


>## Activity
>
> Consider this riddle: A father and son get in a car crash and are rushed to the hospital. The father dies. The boy is taken to the operating room and the surgeon says, “I can’t operate on this boy, because he’s my son.” How is this possible? 
>
>
> >## Solution
> >
> > The surgeon is a woman. 
> > In research conducted on 197 BU psychology students (where women outnumbered men two-to-one) and 103 children, ages 7 to 17, only a small minority of subjects—15 percent of the children and 14 percent of the BU students—came up with this answer. Of self-described feminists in the student group, a majority, 78 percent, did not guess the surgeon was the mother. This illustrates how a training dataset may unintentionally come to encode societal gender bias through human applied labels such as "Surgeon" vs. "Female Surgeon". 
> >
> > 
> {: .solution}
{: .challenge}

>## Note
>
> Data bias here is not to be confused with the ["bias term"](https://developers.google.com/machine-learning/glossary#bias-math) also used in machine learning or statistical terms such as [bias-variance trade-off](https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff).
{: .callout}


## When might human bias enter a machine learning pipeline?

There are abundant opportunities for human bias to enter ML systems at all stages of the pipeline including:

* When the study is being designed
* When datasets are constructed
* When decisions are being made to refine and reinforce a models learning 
* When interpreting and applying decisions made by the model to real world scenarios

### Bias arising in the study design

Some machine learning systems are quite simply built on ethically unsound foundations from the outset. A recent controversial study, [Tracking historical changes in trustworthiness using machine learning analyses of facial cues in paintings*](https://www.inputmag.com/culture/this-algorithmic-study-about-trustworthiness-has-some-glaring-flaws), published in Nature Communications, garnered significant controversy for its proximity to the thoroughly debunked pseudoscience [phrenology](https://en.wikipedia.org/wiki/Phrenology) which aims to assess an individuals personality and (or in the case of this study, trust) based on facial structure. 

### Bias arising in dataset collection and construction

> "It’s all too easy to forget that data is about human beings and their behaviors. Data is not an abstraction...Data encodes the stories of our lives, capturing not only our tastes and interests but also our hopes and fears. Data isn’t an abstract idea or a set of numbers or qualitative responses. It can be and is, ultimately, human. (reference)"
> 

Data is never neutral. It is about people. And the manner in which data is sourced and constructed for training sets will have important implications on your model's output. In the simplest example, if you are aiming to build a face recognition software but only train your model on a dataset of white faces, your model is obviously going to struggle to identify faces of any other colour. 

So how is data typically collected? Because of the many complexities around copyright and licensing, privacy issues and high costs involved in getting access to large quantities of quality datasets, data scientists have favoured scraping what they can find freely, en masse and indiscriminately, across the internet from free sources such as [Wikipedia](https://aws.amazon.com/de/datasets/wikipedia-xml-data/), FlickR or Google News. aken without intervention, these Datasets collected in this manner, taken without intervention, will reflect the biases of these sources, such as a certain demographic composition (overrepresentation of young internet users from developed countries for example). 

#TODO Example of word embeddings issue http://europepmc.org/article/MED/29615513

In recent years there has been talk about GLAM institutions being part of the change here in creating curated sets of more rigour. #TODO reference the paper here 

Training data is enriched and labelled so as to highlight the features you want your model to recognise and as we saw in the first activity, bias can crop up, either consciously or unconsciously, in the course of this. GLAM staff will be more than familiar with this issue as we grapple with [historical bias in library and archives descriptions](https://cataloginglab.org/list-of-statements-on-bias-in-library-and-archives-description/) for instance. As demand for GLAM collections and catalogue data for use in machine learning increases, it is vital that model builders are made aware of the biases that may be encoded within cultural heritage data. Whether personally undertaking or crowdsourcing your data annotation, including outsourcing to a service such as Amazon's Mechanical Turk, it's important to be aware of how different demographics and social constructs may introduce bias and implicit associations into your pipeline at the data annotation stage.

[insert image]

>## Activity
>
> Consider this image and write a list of terms you would use to annotate it. Compare your outputs with your nearest neighbour(s). Discuss the differences and how this could effect a model. How might you mitigate these differences in annotations?
{: .challenge}


### Bias arising when refining and reinforcing a models learning
 
We've talked alot about bias that can make it into our training data, but this isn't the only way it manifests itself in machine learning systems. As we now know from earlier in this lesson, machine learning models are refined and reinforced based on reactions to its results. In this process, there is a risk of certain outcomes being ignored and others privileged over others, skewing a models learning.

For example, a model builder is using named entity recognition across multilingual newspapers. They might determine they are satisfied when the model gets to 90% accuracy and will aim to improve to this result. However this overall accuracy can hide the fact that some particular ‘slices’ of our data might have much worse accuracy. Your overall accuracy might be very good but your model may underperform on one language. This might not be addressed by changing your data but changing how you approach training and evaluating your model.

### Bias arising in the application of machine learning decisions to real world scenarios  

This may be an area you might already have some awareness of as the ubiquity of machine learning systems in our lives increases, the effects of unfair, biased algorithms are starting to become more apparent. Predictive policing as covered earlier is probably the most clear example of algorithmic bias. Algorithmic bias is defined as unjust, unfair, or prejudicial treatment of people related to race, income, sexual orientation, religion, gender, and other characteristics historically associated with discrimination and marginalization, when and where they manifest in algorithmic systems and algorithmically aided decision-making. #TODO add more examples (loan applications, etc)

It is imperative to be aware then that the manner in which data is collected, annotated and results applied, will have far reaching consequences for society as decisions produced by ML systems are increasingly being relied upon in real world scenarios. From seemingly benign systems like recommendation engines to predictive policing, opportunities for ML systems to perpetuate and amplify humans bias and inequality abound. 

## Common bias types in machine learning 

Let's take a closer look at some specific and common types of bias that may manifest in the undertaking of machine learning approaches at your institution. This is of course only a small handful of potential sources of bias that may affect our judgment and skew a model's predictions. It's important for model builders to be vigilant about finding and remedying bias in whatever form it may enter the machine learning pipeline. 

|Type|Definition|Example|
|----|----|----|
|Prejudice bias | |The classic example used to describe this bias is a machine learning model that’s designed to differentiate between men and women in pictures. The training data contains more pictures of women in kitchens than men in kitchens, or more pictures of men coding than women, then the algorithm is trained to make incorrect inferences about the gender of people engaged in those activities due to prejudices that occur in the real world, represented in the data.|
|Selection bias| Introduced by the selection of individuals, groups or data for analysis in such a way that proper randomization is not achieved, thereby ensuring that the sample obtained is not representative of the population intended to be analyzed | A model is trained to predict future sales of a new product line for the museum gift shop. To build the training set, the first 200 subscribers to the museum's newsletter were offered a small gift voucher to fill in a survey. Instead of randomly targeting consumers, the dataset targets newsletter subscribers who don't necessarily represent the museum's potential paying customers. It's entirely possible the newsletter subscribers population may be more inclined to be signed up to learn about free events and giveaways, while typical consumers may not be enticed by small gift vouchers or even signed up at all.|
|Confirmation bias| In the process of refining and reinforcing a models learning, unconsciously or consciously processing data in ways that confirm preexisting beliefs and hypotheses.|| 
|Correlation bias| Correlation is not causation ||
|Exclusion bias| Removing data from a set that we think isn’t relevant | |

## How can GLAM staff help manage bias in machine learning approaches?

> Archives are the longest standing communal effort to gather human information and archive scholars have already developed the language and procedures to address and discuss many challenges pertaining to data collection such as consent, power, inclusivity, transparency, and ethics & privacy. [pdf](https://dl.acm.org/doi/pdf/10.1145/3351095.3372829)
> 

The presence of bias in the classifications and predictions of machine learning is a key challenge today, but being aware of and transparent about the problem allows us to take proactive steps to mitigate their effects. For GLAM professionals, this is familiar ground and in "Reference Lessons from archives: strategies for collecting sociocultural data in machine learning" the authors argue that the document collection practices in archives present the ideal ethical and practical framework for mitigating bias in data collection for the field of machine learning. GLAM professionals have an opportunity to apply these tools to the management of bias,

“That means,” said Catanzaro,“that the collection and curation of data sets, the skills that you guys practice—the resources that you have access to—can enable the creation of new algorithms and new applications.”(Catanzaro, 2019, 5:30)

How else might GLAM staff actively help manage bias in machine learning approaches?

* Hire a diverse workforce in general, professional skills is not enough #TODO (collections as data reference)
* Contribute diverse language materials, collections and texts to sources where model builders are finding their data such as Wikipedia
* Collaborate directly with computer scientists to build new diverse data sets for use in machine learning (#TODO reference Arabic HTR here)
* Enlist the help of staff with the right domain expertise to review training data construction before and after, they may see biases that you have overlooked
* When collecting and annotating data make sure to recruit diversified crowds for the task and carefully communicate instructions
* Employ toolkits for detecting and removing bias from machine learning models, for instance the IBM open sourced [AI fairness 360 tool] (http://aif360.mybluemix.net/) 
* Consider your partnerships and collaborators closely, including ramifications of outsourcing your AI to external companies/partners
* Know your data and be transparent about it by creating a Factsheet describing and documenting it in full. 

## Activity
>
> In small groups, consider the following potential machine learning project. Discuss 2-3 potential points at which bias may enter the pipeline, and questions/strategies GLAM staff might want to consider in order to manage it: 
> *An art museum is keen to make a newly acquired digitised collection of 20,000 Southeast Asian photographs more discoverable within the main museum image search. Aside from a collection level description noting the provenance of the collection from a 19th century English explorer, the individual images have very little in the way of item level description except for some captions ascribed by the collector. A model will be trained to classify these images. In order to build the training data set, the art museum is considering setting up a public crowdsourcing project is set up asking members of the public to tag a set of images with as many descriptive words as they can.* 

{: .challenge}


>## Resources Consulted & Recommended Reading
>
> - Catanzaro, B. (2019, December 4). "Datasets make algorithms: how creating, curating, and distributing data creates modern AI." [Video file]. Retrieved from [https://library.stanford.edu/projects/fantastic-futures](https://library.stanford.edu/projects/fantastic-futures)
> - Coleman, C. N. (2020). Managing Bias When Library Collections Become Data. International Journal of Librarianship, 5(1), 8–19. https://doi.org/10.23974/ijol.2020.vol5.1.162 
> - Ekowo, M., 2016. Why Numbers can be Neutral but Data Can’t. [online] New America. Available at: <https://www.newamerica.org/education-policy/edcentral/numbers-can-neutral-data-cant/> [Accessed 23 March 2021]
> - Eun Seo Jo and Timnit Gebru. 2020. Lessons from archives: strategies for collecting sociocultural data in machine learning. In Proceedings of the 2020 Conference on Fairness, Accountability, and Transparency (FAT* '20). Association for Computing Machinery, New York, NY, USA, 306–316. DOI:https://doi.org/10.1145/3351095.3372829
> - Mayson, Sandra Gabriel, Bias In, Bias Out (September 28, 2018). 128 Yale Law Journal 2218 (2019), University of Georgia School of Law Legal Studies Research Paper No. 2018-35, Available at SSRN: https://ssrn.com/abstract=3257004
> - Padilla, T. (2019). Responsible Operations: Data Science, Machine Learning, and AI in Libraries. OCLC ResearchPosition Paper. https://doi.org/10.25333/xk7z-9g97
> - Rich, B., 2014. BU Research: A Riddle Reveals Depth of Gender Bias [online] Boston University. Available at: <https://www.bu.edu/articles/2014/bu-research-riddle-reveals-the-depth-of-gender-bias/> [Accessed 22 March 2021] 
> - Rehumanized Crowdsourcing: A Labeling Framework Addressing Bias and Ethics in Machine Learning [pdf](https://www.natabarbosa.com/chi_rehumanized_crowdsourcing.pdf)
> 
{: .checklist }
