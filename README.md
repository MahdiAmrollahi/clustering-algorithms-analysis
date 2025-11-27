# Clustering Algorithms Analysis

Hands-on exploration of clustering techniques across three progressively more complex case studies. Each notebook focuses on a slightly different learning goal—from writing K-Means from scratch, to applying scikit-learn on a labeled agronomy dataset, to comparing multiple clustering paradigms on wine chemistry features.

## Repository Tour
- `kmeans-from-scratch/2.ipynb` – builds every step of K-Means with NumPy on the 2D Iris subset, including visualization of convergence.
- `wheat-kmeans/1.ipynb` – uses scikit-learn to cluster the Wheat Seeds dataset, demonstrates the elbow method, and compares predicted clusters with ground-truth species labels.
- `wine-clustering-study/3.ipynb` – end-to-end study that scales/normalizes features, reduces dimensionality with UMAP, and benchmarks six clustering algorithms (K-Means, Mean Shift, Gaussian Mixture, Affinity Propagation, DBSCAN, OPTICS).
- `wheat-kmeans/seeds.csv` and `wine-clustering-study/wine-clustering.csv` – source datasets kept locally for reproducibility.

## Environment Setup
The notebooks rely on a light scientific Python stack. A recent Python 3.10+ interpreter is recommended.

### Create an isolated environment
```powershell
python -m venv .venv
.venv\Scripts\activate
pip install --upgrade pip
pip install numpy pandas matplotlib seaborn scikit-learn umap-learn
```
> `umap-learn` pulls in `numba`; on Windows it may take a minute to compile wheels the first time.

### Launch Jupyter
```powershell
pip install notebook          # if you do not already have it
jupyter notebook
```
Open any notebook via the Jupyter UI to reproduce the figures and experiments.

## What You’ll Learn
- **Algorithm fundamentals:** Implementing distance metrics, centroid updates, and stopping criteria from scratch.
- **Practical model tuning:** Using WCSS and the elbow method, experimenting with `init`, `n_init`, `max_iter`, and understanding their trade-offs.
- **Advanced comparisons:** Evaluating how centroid-, distribution-, and density-based clustering algorithms behave on the same embedding space (including runtime tracking).
- **Visualization workflow:** PCA and UMAP projections, scatter plotting helper utilities, and side-by-side comparisons of predicted vs. true labels.

## Reproducing the Studies
1. Start Jupyter and open the desired notebook.
2. Run all cells sequentially (`Kernel > Restart & Run All`) to regenerate figures.
3. Modify the marked experiment cells (e.g., change `n_clusters`, swap initializers, tweak DBSCAN `eps/min_samples`) to observe sensitivity.

## Suggested Next Steps
- Add `requirements.txt` or `environment.yml` if you plan to share the project widely.
- Export key plots (e.g., elbow curve, UMAP cluster maps) to `figures/` so they can be referenced outside notebooks.
- Consider adding a short write-up comparing metrics (Silhouette score, Davies–Bouldin) to complement the qualitative visual analysis.

Feel free to fork and extend with additional datasets or clustering algorithms (e.g., Spectral Clustering, HDBSCAN) to broaden the comparison set.
