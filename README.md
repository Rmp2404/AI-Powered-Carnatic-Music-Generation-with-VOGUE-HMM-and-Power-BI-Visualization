# AI-Powered-Carnatic-Music-Generation-with-VOGUE-HMM-and-Power-BI-Visualization

## Overview

This repository contains an end-to-end pipeline for Carnatic Classical Music generation using:

* Librosa + Python for extracting swaras (musical notes) from raw .mp3 audio files.

* VOGUE (Variable Order and Gapped Hidden Markov Model) for learning melodic patterns and generating new music sequences.

* Power BI for insightful data analysis and visualization of swara transitions and raga characteristics.

## Problem Statement

Indian Classical Music, especially Carnatic, follows structured melodic rules governed by ragas. The goal of this project is to:

* Extract accurate swara sequences from audio clips.

* Train the VOGUE model on extracted sequences to generate new musical content.

* Analyze and validate the output using Power BI dashboards.

* Explore raga-specific generation, and document the limitations faced.

 ## Dataset

* Name: Saraga Carnatic Music Dataset

* Source: Kaggle - Saraga Carnatic Dataset

* Contents: 197 Carnatic music audio files (.mp3) with accompanying JSON metadata files indicating raga.

## Workflow Summary

#### 1) Swara Extraction (Google Colab)

* Loaded .mp3 files using Librosa.

* Extracted pitches via librosa.piptrack().

* Converted pitches to Carnatic swaras using fundamental ratios.

* Saved as extracted_swaras.csv.

##### Output: Swara sequence data (~100,000 swaras).

#### 2) VOGUE Model Training

* Implemented a Variable Order & Gapped HMM (VOGUE).

* Trained on the complete swara sequence dataset.

* Generated 50-note sequences using learned patterns.

#### Output: Novel swara sequences imitating Carnatic structure.

#### 3) Raga-Conditioned Training (Attempted but Not Effective)

* Attempted raga-specific VOGUE models.

* Problem: Sparse data per raga (only 1-2 clips/raga, insufficient context).

#### Result: Overfitting and incoherent sequences.

#### 4) Swara-to-Audio Conversion

* Setup using Pydub/Scipy to convert generated swaras to simple audio tones.

#### 5) Power BI Visualization

Power BI Report: AI-Powered Carnatic Music Generator_Power BI Visualization.pbix includes:

## Visualization                                                                            

Swara Frequency Distribution - Real vs Generated swara occurrence count

Raga-wise Swara Bar Chart - Swara usage per raga

Swara Transition Heatmap - Frequency of swara-to-swara transitions

Sankey Diagram (Swara Flow) - Major swara flow paths in sequences

Tooltip-Enabled Pages - Explanation of visuals for better user understanding

## Future Improvements

* Train RNN/Transformer-based models for better raga control.

* Include Tala (rhythm) features.

* Extend dataset with more raga recordings.

* Deploy an interactive web-based Carnatic generator.

