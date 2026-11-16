---
name: cluster-report
description: Try at least three clustering algorithms on a dataset the user describes, select one, and write a one-page report that presents only the selected clustering. Only runs when invoked explicitly with /cluster-report.
disable-model-invocation: true
---

The user gives the data file, the feature columns, the ID column, any known-label column, a seed and an output
folder, either as $ARGUMENTS or in the message. Ask once if the file or the feature columns are missing. Do not
assume anything else about the data.

1. Check the data. Report n, p, missing values and the range of the feature standard deviations, and note any
   preprocessing the user says was already done. The ID and any label column are never used for fitting, tuning
   or selection. Labels may only be used in step 7, after the method is fixed.
2. Preprocess. Center every feature. Standardize features only if they are in different units; if they share
   one scale, keep it and say so. When p is larger than n, cluster on the leading principal components, enough
   to pass 50% of the variance and at most 10, and state the number. Every algorithm gets the same input matrix.
3. Algorithms. Fit at least three from different families: K-means (25 or more random starts), hierarchical
   clustering (Ward and average linkage, the linkage is a tuning choice), and spectral clustering
   (nearest-neighbor affinity, two or three neighbor counts). PCA or UMAP is an embedding, not a clustering
   algorithm, and does not count toward the three.
4. Tune. For each algorithm and setting, try K = 2 up to the smaller of 6 and n/5. For every candidate record
   (a) the mean silhouette on the input matrix, (b) the smallest cluster size, and (c) stability, the mean
   adjusted Rand index between the full-data labels and the labels from refitting on 50 random 80% subsamples
   drawn with the seed, compared on the shared observations.
5. Select with a fixed rule, written before looking at any label. Drop candidates with a cluster smaller than
   the larger of 3 and 5% of n. Keep those with stability of at least 0.75; if none pass, keep the three most
   stable and say that the structure is weak. Among those take the highest silhouette. Candidates within 0.01
   silhouette of it are ties, broken by higher stability, then smaller K, then the order K-means, hierarchical,
   spectral. State the rule and the winning numbers in the report.
6. Present one method only. The other algorithms get one sentence that names them and says by which criterion
   they lost. Do not show their labels, cluster sizes, plots or tables. For the selected clustering make one
   figure about 6.5 x 2.7 in with two panels. Left: the observations on the first two principal components,
   colored by cluster in Okabe-Ito colors, marker shape by known label if one was given, and the ID printed
   next to any observation with a negative silhouette. Right: silhouette and stability against K for the
   selected algorithm and setting, with the chosen K marked. Add one table with a row per cluster: size, mean
   silhouette, the count of each known label if given, and the three features with the largest standardized
   mean difference from the rest.
7. Interpret. Say what separates the groups, how well separated they are (a silhouette under 0.25 is weak
   structure, say it plainly), and which observations sit between groups. If labels were given, cross-tabulate
   them with the clusters now and report the adjusted Rand index, and state that they played no part in the
   selection. Limitations to cover when they apply: small n, a result that depends on the preprocessing or on
   K, internal criteria that reward compact round clusters, and that every algorithm returns clusters even when
   there are none. Every number must come from output printed in this run.
8. Report. Write one self-contained HTML file (figure embedded) and the script that made it in the output
   folder. Letter paper, 0.5 in margins, 11-point text. Order: title line (data, n, p, seed, author if given),
   data and preprocessing, algorithms and selection rule, figure, table, findings, limitations.
   The report is limited to one printed page, including all text, figures and tables, and shows clustering
   results from only the one selected method. Print it to PDF with a headless browser and count the pages. If
   it runs over, cut words first, then shrink the figure, and never drop the figure, the table or go below 10
   points. End your reply with the page count, the selected method and the files written.
