---
title: "Day Two Group Assignment Part Two"
teaching: 20
exercises: 55
questions:
- "What are the likely side-effects in a data analysis pipeline?"
- "How can I create a bipartite visualizations in R?"
- "What does it take to calculate ecological networks metrics?"
objectives:
- "Articulate benefits / downsides of data"
- "Discover limitations of traditional analysis and visualizations"
keypoints:
- "Working with big datasets often requires different tools and skills"
- "Data processing introduces errors and bias"
- "Many tools are suited for small datasets only"
---

In this session, we'll go through the steps from acquiring data, to "cleaning" data, to visualizing and analyzing the results.

First, we'll have a look at likely side-effects of preparing data for analysis and visualization.

## Side-effects of Preparing Data 

Data may be reformatted and "cleaned" to help facilitate analysis, visualization, and re-use. 

In this exercise, we'll look at a specific dataset and it's transformations in the GloBI processing pipeline.

This example pipeline likely reflects other research data processing (automated or manual) techniques in use today. 


> ## `Exercise 1. Data Processing Side-effects`
>
>1. Re-visit the GloBI process page at [https://globalbioticinteractions.org/process](https://globalbioticinteractions.org/process) . 
>
>2. Locate the original dataset related to Olito, Colin; Fox, Jeremy W. (2015), Data from: Species traits and abundances predict metrics of plant–pollinator network structure, but not pairwise interactions, Dryad, Dataset, [https://doi.org/10.5061/dryad.7st32](https://doi.org/10.5061/dryad.7st32) . 
>
> 3. Now, locate the manually transcribed version ```interactions.tsv``` of this dataset at [https://github.com/zedomel/olito2015](https://github.com/zedomel/olito2015).
>
> 4. Inspect a version of the same dataset as seen by GloBI before taxonomic linking at [https://depot.globalbioticinteractions.org/reviews/zedomel/olito2015/indexed-interactions.csv](https://depot.globalbioticinteractions.org/reviews/zedomel/olito2015/indexed-interactions.csv) 
>
> 5. Inspect dataset version after GloBI's taxonomic linking at [olito2015.csv](../data/olito2015.csv)
>
>6. Compare the different versioned of the dataset and describe the similarities and changes. Note where in the process diagram the datasets live.
>
>
{: .challenge}


Now, let us have a look at visualizing and analyzing network data. 


### Visualization: Bipartite and Pre-canned Data


> ## `Exercise 2. Looking at Pre-canned Data` 
>
> 1. Locate a populate R package by doing a web search for "bipartite R package"
> 
> 2. In the R package page, notice the "starting with bipartite" vignette. 
>
> 3. If feasible, install package in your R environment
>
> 4. Reproduce the bipartite visualization vignette example with the ```olito2015``` network .
> 
{: .challenge }

Notice how much time it take to setup an environment and reproduce a "getting started" example. 


## Visualization: Bipartite and "Real" Data

Some biodiversity data infrastructures (like GloBI, GBIF) hide the complexities of working with big datasets by offering Web-accessible API (Application Programming Interfaces). Instead of getting all the data on your system, you ask for a specific subset of the data, and let some remote server do the heavy lifting. In this exercise, we'll use an API that GloBI provides through the rglobi package.

> ## `Exercise 3. Plot a bipartite visualization with "real" data`
> 
> 1. use the ```rglobi::get_interactions_by_taxa``` method to retrieve records describing Fungi interacting with Oak trees (Quercus). Alternatively, use the [GloBI Browser](https://globalbioticinteractions.org/browse) to do a similar web query.
> 
> 2. save the results in a csv file 
> 
> 3. count the number of records in the csv file
> 
> 4. use this csv file to re-create the bipartite visualization of the first exercise
>
{: .challenge }

Feel free to use the [cheatsheet](../code/cheatsheet.nb.html).

### Analyzing Lots of Data

To prepare for this workshop, you downloaded one of GloBI's data products, the interactions.csv.gz from the https://globalbioticinteractions.org/data page.


> ## `Exercise 4. Counting all the things`
>
> 1. count the number of records in ```interactions.csv.gz```
>
> 2. (extra credit) count the number of records that contain "Fungi" in them 
>
> 3. (extra credit) count the number of record that contain both "Fungi" and "Quercus" in them
>
{: .challenge }

Please feel free to use any tool you'd like. Also, please see the [Big Data Cheatsheet](../code/cheatsheet.txt). 

Also, for your convenience, please see files [oakfungi-sample.csv](../data/oakfungi-sample.csv) and [oakfungi.csv](../data/oakfungi.csv) for examples of results. 


> ## `Exercise 5. Visualizing all the things`
>
> 1. create a bipartite graph for [oakfungi-sample.csv](../data/oakfungi-sample.csv)
>
> 2. now, create a bipartite graph for [oakfungi.csv](../data/oakfungi.csv)
>
> 3. compare the visualization and notice the differences
>
{: .challenge }

The bipartite r package contains various methods to quantitatively describe networks. 


> ## `Exercise 6. Exploring Network metrics `
>
> 1. re-visit the [bipartite vignette pdf](https://cran.r-project.org/web/packages/bipartite/vignettes/Intro2bipartite.pdf) 
> 
> 2. in the vignette, look for the network, group, link, and species metrics (or indices)
>
> 3. (extra credit) calculate some indices using [oakfungi-sample.csv](../data/oakfungi-sample.csv) or [oakfungi.csv](../data/oakfungi.csv) datasets. 
>
{: .challenge }

Now that we've tried a couple of ways to access, visualize, and analyze data, let's reflect on how these methods fit into a research workflow. 

> ### `Discussion```
>
> 1. What are the benefits to using a whole dataset like GloBI's ```interactions.csv.gz``` ? 
>
> 2. What are the benefits of using the GloBI Web API instead? 
>
> 3. What method would you choose for your publication?
>
> 4. How would you cite / publish your results?
>
> 5. How would you assess the quality of the retrieved data?
{: .discussion }


## What's Next?

Please see [schedule](../#schedule) for our next collaborative activity. 
