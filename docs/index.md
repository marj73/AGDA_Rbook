---
title: "Advanced Geospatial Data Analysis with R -- Applications in Geosciences"
author: "Dr. Marj Tonini, Haokun Liu"
date: "09/12/2024"

output:
  bookdown::pdf_document2:
    number_sections: true
    toc: true
  bookdown::gitbook:
    config:
      toc_depth: 2

editor_options: 
  chunk_output_type: inline
  markdown: 
    wrap: sentence
    urlcolor: blue

bibliography: book.bib
csl: taylor-and-francis-chicago-author-date.csl
link-citations: true
number_sections: true
new_session: true
language:
  ui:
    chapter_name: "Chapter "

output_dir: docs
book_filename: "fake-book"
---



# Preface {.unnumbered}

Earth surface environmental processes exhibit distinctive characteristics, encompassing both spatial and temporal dimensions, along with various attributes and predictive variables.
Coupled with uncertainty and complexity issues, all this contributes to make this field of research highly challenging.
Furthermore, in the era of Data Science, the wealth of available data and the rapid development of analytical models have emerged as distinctive aspects in the realm of **Advanced Geospatial Data Analysis (AGDA)**.
The domain of AGDA encompasses data exploration, manipulation, and modelling, from the acquisition phase up to the visualization and interpretation of the results.
Mapping where events are located and how they relate to each other provides a better understanding of the process being studied.
Finally, as an increasing volume of geo-environmental data becomes more and more accessible, the demand for spatial data scientists is growing rapidly, both in public research institutions as well as in private companies.

The term "**Data Science**" was defined for the first time by Peter Naur in 1974 as "*the science of dealing with data, once they have been established, while the relation of the data to what they represent is delegated to other fields and sciences*" [@naur_peter_concise_1974].
In essence, this definition frames Data Science as the technical and methodological handling of data, while their initial creation or gathering, as well as the interpretation of its meaning in the broader context, is not the primary focus of this discipline.
In 1977 the International Association for Statistical Computing ([IASC](https://iasc-isi.org/)) further refined the concept of Data Science, emphasizing its role in the process of transforming raw data into valuable information and actionable knowledge.
The IASC articulated that Data Science involves not only the collection and processing of data, but also the application of statistical methods and computational techniques to extract meaningful insights, which can then be used to support decision-making and drive innovation across various domains.

In disciplines like environmental and earth Sciences, physical geography, humanities and social sciences, the use of Data Science procedures is emerging only recently, proving to be extremely efficient to deal with the complexity of the investigated process and the heterogeneity of the underlying data sources [@amato_spatiotemporal_2022].
This leads to a cultural shift, moving scientists away from individual working within their own research domain.
Indeed, disciplinary boundaries are more and more permeable, pushing scientists to be more open to collaborate among them and with decision makers on the investigation and understanding of real-world problems.
Modern earth and environmental scientists need to interact with other disciplines, apparently far from their domain.
This openness is increasingly important as society struggles to respond to the implication of anthropogenic pressures on different issues, such as natural hazards and climate change, or the harmful impacts of human activities on biodiversity, water and air quality, human health.

## Book overview {.unnumbered}

This eBook primarily focuses on introducing analytical techniques from the field of Data Science to analyze and understand environmental processes occurring on Earth's surface.
Mastering the methodologies in this multidisciplinary and rapidly evolving field—encompassing statistics, mathematics, geomatics, and computer science—can be a challenging endeavor.
To address this, the eBook maintains a rigorous foundation in mathematical and statistical principles while emphasizing practical applications within the domain of Geosciences.

Emphasis is placed on the application of advanced geospatial tools to analyze and model both natural and anthropogenic hazards, as well as land-use processes.
Theoretical concepts are reinforced through case studies employing spatial clustering techniques and both supervised and unsupervised machine learning algorithms.
Examples include stochastic point process models for spatio-temporal cluster analysis and machine learning-based approaches for geodemographic segmentation, susceptibility assessment, and risk mapping.

### Computing lab {.unnumbered}

Computations are conducted using the R free software environment, which is specifically designed for data analysis and manipulation.

After a brief introduction to the main functionalities in R (see Chapter \@ref(intro)) and an overview of the basic operations with geospatial data (see Chapter \@ref(geodata)), the rest of the chapters will focus on the following geo-computational techniques:

-   *Exploratory Data Analysis and Visualization*: examining geographical variations in statistical data distributions, including Geographically Weighted Summary Statistics (Chapter \@ref(gwss)).
-   *Cluster Detection and Mapping*: using global clustering methods, namely Ripley's K-function and Kernel Density Estimator (Chapter \@ref(kde)).
-   *Random Forest*: as example of supervised machine learning algorithm. We present both the global (Chapter \@ref(global-rf)) and the local version, and we use Random Forest to introduce interpretability & explainability in machine learning (Chapter \@ref(local-rf)) .
-   *Self-Organizing Maps*: as example of unsupervised machine learning method for data clustering/segmentation and visualization (Chapter \@ref(som)).
-   *Feature detection*: using DBSCAN for identifying and visualizing clustering features (Chapter \@ref(dbscan)).

To complete the applied computing labs presented in each chapter, readers can download the datasets from here: [dataset](data)

### Target audience {.unnumbered}

The target audience includes master's and PhD students in Earth and Environmental Sciences, Biology and Spatial Ecology, Physical Geography, and related disciplines.
Our goal is to empower students by guiding them through both theoretical knowledge and hands-on practical applications, helping them develop strong problem-solving skills.

**This eBook aims to equip the audience with**:

-   A solid understanding of key practical concepts and applied aspects in AGDA.
-   Advanced tools to effectively navigate and analyze spatial datasets in Geosciences.

The eBook is designed for intermediate to advanced R users with previous experience in geospatial data analyses and a keen interest in geocomputing.
If you have only a basic knowledge of these areas, we strongly encourage you to explore the essential references provided in each chapter.
These resources offer valuable documentation and additional materials to help deepen your understanding.

**The main prerequisites are the following**:

-   Knowledge of basic statistics: methods of descriptive statistics (measures of central tendency and dispersion); how to assess relationships between variables; concepts of correlation and regression.
-   Basic knowledge in geomatics (GIS): basic operations with raster and vector datasets.
-   R programming basics and RStudio.

## Authors information {.unnumbered}

**Marj Tonini** is a spatial data scientist with a profound expertise in geospatial modeling for risk assessment, particularly in relation to wildfires and landslides.
She earned her Ph.D. in 2002 from the [Sant'Anna School of Advanced Studies](https://www.santannapisa.it/en) in Pisa, Italy, where she developed a thesis on agro-environmental modeling that laid the foundation for her career.
In 2004, she joined the [University of Lausanne](https://www.unil.ch/central/en/home.html) (UNIL) as a postdoctoral researcher in geospatial data analysis, and by 2008, she was appointed as Senior Research Manager at the [Institute of Earth Surface Dynamics](https://www.unil.ch/idyst/en/home.html), where she continues to serve in her current role.
Sine 2022 she has been servig a four-year term as the director of the [Swiss Geocomputing Centre](https://unil-sgc.github.io/) of the Faculty of Geosciences and environment (UNIL)

Marj's research focuses on the development of innovative methodologies that facilitate the efficient extraction of knowledge from complex environmental datasets.
Her work aims to estabilishing a robust methodological framework to understand the spatio-temporal dynamics of environmental processes and to evaluate the influence of various predictor variables.
Her current research focuses on the analysis of land use and land cover changes, alongside the development of predictive scenarios and the assessment of susceptibility and risks associated with natural hazards.
Through this work she seeks to advance the field of geospatial science by translating data-driven insights into practical solutions for managing and mitigating environmental risks.
You can find the full list of her publications on [ResearchGate](https://www.researchgate.net/profile/Marj-Tonini-2) and [Google Scholar](https://scholar.google.it/citations?user=qXexP-IAAAAJ&hl=en).

Marj has written the vast majority of this book.
Her contributions include the development of the conceptual framework, writing the theoretical background chapters, developing case studies, designing methodologies, conducting data collection and analysis, and software/tool development.
The following section "*My Journey of Learning*" refers to her personal experience.

**Haokun Liu** is a Ph.D. student at the Group of [Cities and Dynamics of Networks](https://wp.unil.ch/citadyne-news/), [University of Lausanne](https://www.unil.ch/central/en/home.html).
In addition to his doctoral studies, he serves as a student assistant at the [Swiss Geocomputing Center](https://unil-sgc.github.io/).
Benefiting from rigorous and comprehensive training in both China and Switzerland, Haokun has developed a diverse research portfolio.
His primary research interests and experience encompass a wide range of interdisciplinary fields, including urban analytics, health geography, and spatial data science.
His work focuses on leveraging advanced computational techniques to address complex urban and environmental challenges, bridging the gap between data-driven insights and real-world applications.

Haokun's contributions were instrumental in establishing and managing the GitHub repository used to host and maintain this eBook.
He also played a key role in data visualization and mapping, and provided valuable revisions to the applied computing labs.

## My Journey of Learning: Integrating Geospatial Data Analysis with Data Science {.unnumbered}

In the early 2000s, as I (Marj) embarked on my PhD journey, a new frontier was beginning to unfold in Geosciences.
Geographical information systems (GIS) were just starting to make waves, offering a fresh perspective on how researchers could investigate and understand the environment.
It was through my thesis on the effects of spreading olive vegetation water on agricultural land that I first delved into the world of GIS.
This early exposure was more than just a technical skill; it was a revelation that would drive me to explore the depths of spatial analysis for years to come.

After completing my PhD, my journey led me to a PostDoc position where I had the privile of working with Professor [Mikhail Kanevski](https://www.egu.eu/awards-medals/ian-mcharg/2022/mikhail-kanevski/), a true pioneer in the fields of environmental data mining, geostatistics, and the emerging field of applying machine learning to spatial environmental data.
In this dynamic research team, I found myself diving headfirst into the world of spatial data science, driven by the desire to uncover valuable insights from the complex data that described our environment.
The work was challenging, yet it was also exhilarating, as every new technique I learned brought me closer to understanding the intricate tapestry of environmental phenomena.

As the years passed, the tools and resources available to researchers like me grew exponentially.
The development and widespread adoption of free programming languages like and [R](https://www.r-project.org/) and [Python](https://www.python.org/) revolutionized the way we approached statistical analysis and machine learning.
What was once the domain of a select few became accessible to many, thanks to the wealth of pre-developed scripts and resources these languages offered.
For me, and for countless others, this accessibility was a game-changer.
It meant that advanced techniques were no longer out of reach, and it fostered a culture of greater reproducibility in research.
By utilizing standardized, widely adopted open-source programming languages and cloud-based platforms for hosting and managing Git repositories, such as [GitHub](https://github.com/), researchers can now more easily share their code and methodologies, enabling others to replicate and validate their findings.
This collaborative spirit has enhanced the reliability and credibility of scientific research and fostered a community where knowledge is shared and expanded more efficiently.

Reflecting on this journey, I realize that each step – from my early days with GIS to my current role as an independent lead researcher in environmental spatial data analysis in the era of Data Science – has been a chapter in a larger story of discovery and innovation.
It's a story of how spatial data and advanced analytics have become indispensable tools in our quest to understand and protect the environment, and it's a story that continues to unfold with each new challenge and breakthrough.

## Acknowledgements {.unnumbered}

The case studies presented in each chapter came from different projects carried out in collaboration with several colleagues, including master and PhD students.
All the produced scientific papers are duly cited in the bibliography.

I would like to express my gratitude to Professor Mário Gonzalez Pereira and Dr. Joana Parente, for their extensive and fruitful collaboration in investigating the spatio-temporal distribution of wildfires in Portugal.
One of our studies, which explores the evolution of forest fires from spatio-temporal point events to smoothed density maps, forms an integral part of Chapters 3 and 4.

I also thank Professor Stuart Lane and Dr. Natan Micheletti for introducing me to the fascinating world of rock glacier research.
Notably, the 3D point cloud dataset analyzed in Chapter 8 was acquired and processed by Natan during his PhD studies.

My thanks also go to Julien Riese, who produced the input dataset and collaborated with me in developing the code that assesses landslide susceptibility in Canton Vaud, the main focus of Chapter 5.
The same for Axelle Bersier for her meticulous work in acquiring and pre-processing the Swiss national population census dataset, which is used for the exercise on unsupervised learning in Chapter 7.
Both Julien and Axelle exemplify the high caliber of master's students I have had the pleasure of supervising.

For transparency, I acknowledge the use of ChatGPT in assisting with the reformulation of certain sentences in this book and DALL-E to generate the image icon.
