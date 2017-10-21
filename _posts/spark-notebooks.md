# Spark Development Workflows with Data Science Notebooks
October 2017
Two of the most prominent trends in the analytics world over the past 5 years are 
* the use of web-based notebooks for rapid development of code alongside commentary and graphics, facilitating shareability and reproducibility
* the rise of Apache Spark as the primary platform for developing batch and streaming analytics on big data
We have certainly seen these trends in our client work, and enthusiastically support them. We also strongly believe that data science notebooks and Apache Spark have a synergistic relationship. That is, for developing analytics at scale, a natural lifecycle looks like:
\[Prototype code in notebook\] \-> \[Test code\] \-> \[Refactor tested code as a standalone script or package\] \-> \[Test code and deploy in production\]
By keeping the core components of the code in the notebook prototype and the production package in sync, new features can be explored interactively in the notebook and pushed to production when ready. It's really the interactive nature of the notebook that makes it so attractive in this workflow - by making the notebook cells as cleanly separated as possible, data objects and error messages can be inspected at any point in the analytic, then repaired and retested until it works.
In this rapidly evolving ecosystem, several options have emerged that harness Spark from within a notebook. As we have recently navigated through the selection of a development stack for Spark in our client work, we thought it might be worth sharing some of the lessons learned. We went about the process with specific selection criteria for the notebook platform. It should
1. Support Scala and Python at a minimum, and ideally R and SQL as well
2. Be able to connect to Spark in either local or client (YARN) mode
3. Not require any additional licensing \*
4. Retain the wonderful convenience features of Jupyter Notebook: tab completion, syntax highlighting, and inline plotting & graphing
5. Allow use of multiple languages within a single notebook
The candidates we considered included:
* Jupyter Notebook
* Apache Toree
* Apache Zeppelin
* Cloudera Data Science Workbench
* RStudio
\* Disclaimer: our client work is primarily done using Cloudera CDH
## Conclusions
In the end, there is not a clear-cut winner. It's sort of a choose-your-own adventure outcome. 
* Working exclusively in PySpark? Jupyter Notebook will rock your world.
* Working exclusively in R? Ditto for RStudio.
* Want to develop in Scala? Either Toree or Zeppelin will do.
* Really want to switch between languages in a notebook? Zeppelin is your winner.
* Want to do basic graphs on native Spark dataframes? Again, it's Zeppelin.
* Working in Spark 2.2+? Well, maybe not Zeppelin.  
