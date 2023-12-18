# Spectral Clustering

## Overview

This document serves as a guide for the Jupyter notebook containing several key functions related to the exploration and application of the hyperbolic Laplacian in spectral clustering.

## Functions Included

### 1. `adjacency_matrix(image, sigma_intensity=1000, sigma_space=10)`

- **Description**: Constructs an adjacency matrix in List of Lists (LIL) format from a given picture.
- **Input**:
  - `image`: A RGB picture (for our examples we take only low-resolution images to speed up calculations).
  - `sigma_intensity`: A parameter that specifies the similarity of two pixels in intensity.
  - `sigma_space`: A parameter that specifies the similarity of two pixels in coordinate.
- **Output**: 
  - A LIL matrix representing the adjacency matrix of picture pixels.

### 2. `laplacian_eigenmaps(adjacency_matrix, n)`

- **Description**: Computes the eigenvalues and eigenvectors of the Laplacian matrix for a given adjacency matrix.
- **Inputs**:
  - `adjacency_matrix`: The adjacency matrix of the graph in sparse format.
  - `n`: Determining the number of eigenvalues and eigenvectors to compute.
- **Output**: 
  - A tuple of eigenvalues and eigenvectors.

### 3. `hyperbolic_laplacian(g_adj_matrix, alpha_arr=None, symmetrize=False)`

- **Description**: Creates a hyperbolic Laplacian matrix for a given graph represented by its adjacency matrix and a vector of alpha values.
- **Inputs**:
  - `g_adj_matrix`: The aprase adjacency matrix of the graph.
  - `alpha_arr`: A vector of alpha values.
  - `symmetrize`: A additional argument in scipy.sparse.csgraph.lpalacian function, which make matrix symmetric (in our case it's already symmetric).
- **Output**: 
  - The hyperbolic Laplacian sparse matrix.

### 4. `hyp_laplacian_eigenmaps(adjacency, n, alpha=None)`

- **Description**: Computes the eigenvalues and eigenvectors of the hyperbolic Laplacian matrix.
- **Inputs**:
  - `adjacency`: The sparse adjacency matrix of the graph.
  - `n`: Determining the number of eigenvalues and eigenvectors to compute.
  - `alpha`: A 1D numpy array of alpha values for the hyperbolic Laplacian.
- **Output**: 
  - A tuple of eigenvalues and eigenvectors of the hyperbolic Laplacian matrix.

### 5. `segmentation(image, eigenvec)`

- **Description**: Сalculates the segmentation of the picture that corresponds to the given eigenvector.
- **Inputs**:
  - `image`: A RGB picture (for our examples we take only low-resolution images to speed up calculations).
  - `alpha`: Eigenvector of Laplacian matrix.
- **Output**: 
  - Segmented picture.

## Usage

To use these functions in the notebook:

1. Ensure that all necessary dependencies, such as `numpy`, `scipy`, and `matplotlib`, are installed.
2. Import the functions into your Jupyter notebook.
