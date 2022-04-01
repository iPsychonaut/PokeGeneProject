# PokeGeneProject
There exists traceable patterns in Pokemon breeding compatibilities, move-sets, and physical features; these attributes, in theory, represent the backbone of Pokemon evolution and allows us a deeper conversation around their biology. Utilizing multiple data sources, this project is intends to dive into the possible genetic structures of Pokemon evolution through analysis of compiled information, transcribed into RNA by pattern matching and having those sequences then aligned, mapped, and displayed as a phylogenetic tree
NTRODUCTION

The purpose of this compiler is to build a 'genetic' database of Pokemon (also known as Poket Monsters, ポケットモンスター, or Poketto Monsutā) based on their explicit and unique 'move sets', 'body shapes', 'egg groups', and 'types'. For context, the data being compiled is from a fantasy game developed by Nintendo in the mid 1990's that has grown in massive popularity over the past few decades. The game's titular characters are a type of organism that share a single ancestor and have mutated and evolved into various forms based on environment and stress. The gameplay pits these organisms against each other in paper-rock-scissors style combat around strengths and weaknesses; there is a competative scene around this gameplay in the real world. Looking into the nuances of how each Pokemon stacks up against its relatives becomes as gritty as number crunching based on statistics AND move-set managemant based on 'evolutionary form'.

Website resources exist for the purpose of helping those interested in this level of competetion. From official databases to meticulously updated fan-sites and wikis, there is no shortage of data, but they are all in disparate forms. Amongst all this raw data, there existed a very interesting pattern, that seemed to mimic genetic sequences that I have worked with before. Repeated sequences in moves, shared breeding groups, and fundamental typing became the basis of that pattern. Through application of 'translation' from raw data to processable genetic sequences development of a phylogenetic tree with about 90% accuracy was developed based on the first 250 organisms (image above).

This is reworking (v2) of that original web-scrapper and compiler utilizing Pandas, NumPy, Beautiful Soup, and UrlLib. The goal of this notebook is to sheperd the process of developing this project into a GitHub resource. The final accomplishment of a working program should compile the raw data for a list of Pokemon into a CSV file (FinalDatabaseYYYY.MM.DD-HH.MM.SS.csv) for downstream phylogenetics translation. Later additions to this will include the translation of the raw data to genetic information, analysis of molecular variance, phylogenetic processing, and tree imaging.
Data Source Description

The data sources, from Git Repositories to the myriad of websites, all contain disparate data about the organisms that needs to be compiled together: Serebii has move sets, egg groups, form variations; while the Git Repositories contain base stats, alternate forms, as well as organism types. Furthermore, the other resources will be the source of Body Types and Location data to further aid in possible phylogeographic analysis. There are going to be mostly string data coming from these resources, this is optimal as it will provide the best format for 'translation'. The string data will be appended to the current dataframe as extra columns.
GitHub Repository:

This is a fork of the CSV curated by "simsketch". I used it as a basline, added in the most recent releases and corrected a few errors in some later entries. I leave the repository as a fork and pull it here as a Pandas DF. This is the source for Abilities, Types, Stats, and Generation Debut parameters.
Bulbapedia

Bulbapedia is the source for the Body Type parameter. This comes from an image in all Pokemon entries.
Serebii

Currently only Move-sets (Level, Form, TM/HM/TR, Egg Moves, Move Tutor Attackes, Max Moves, and Z Moves) are extracted from Serebii. This comes from a table with words and images in all Pokemon entries.
PokemonDB

PokemonDB is the source for the Egg Group, Gender Ratios, Steps-to-Hatch, and Locations parameters. This comes from a series of tables, and only Egg Group is currently used.
Known Issues:

Currently uses index of 1000+ entries instead of pokedex number to update search
Results & Discussion

The final results of this project currently is an updated CSV file (FinalDatabaseYYYY.MM.DD-HH.MM.SS.csv) that contains updated data from multiple resources (Bulbapeida, PokemonDB, Serebii & Git Repository now). This file will then be used as a basis for 'translation' into genetic sequences that can then have their variance calculated through AMOVA (Analysis of Molecular Variance) which will then provide a means to produce another phylogenetic tree.
CODE TABLE OF CONTENTS:
Section 1) Import Libraries
Section 2) General Utilities
Section 3) Specific Utilities
Section 4) Dataframe Compilers
Section 5) Group Search - Database Builder
Section 6) Single Search - Research Display¶
