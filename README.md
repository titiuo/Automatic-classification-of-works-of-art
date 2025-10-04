# Unsupervised Classification of Artworks  

## 📌 Context  
This project was carried out as part of the **IMA206** course.  
The objective was to **classify digital paintings by style** using unsupervised learning methods, relying only on their visual and semantic characteristics, without any prior labels.  

## 🛠️ Methodology  

### 1. Visual Feature Extraction  
- **Color**: HSV means/standard deviations, dominant palettes via *k-means*  
- **Texture**: GLCM-based statistics (contrast, homogeneity, energy, etc.)  
- **Thematic**: CLIP embeddings (512 dimensions)  

### 2. Deep Representations  
- **ResNet50** pretrained on ImageNet (2048D vectors)  
- **CLIP** embeddings refined on full artworks  
- **Fusion** of descriptors (color + texture + CLIP + ResNet)  

### 3. Dimensionality Reduction  
- **PCA** → 1000 components retained (90% of variance preserved)  

### 4. Unsupervised Clustering  
- **K-means (k=50)**  
- **Cluster labeling**: linked to dominant artists/styles via WikiArt  
- **Optimization** with probabilistic assignment (*softmax* over centroid distances)  

## 📊 Results  
- 26 clusters strongly aligned with identifiable styles (e.g., Impressionism, Rococo)  
- 13 clusters partially coherent  
- 11 clusters ambiguous or inconsistent  
- Clear emergence of stylistically meaningful and interpretable groups  

## ✅ Conclusion  
This project demonstrates that **unsupervised learning** can meaningfully structure a collection of artworks by combining handcrafted descriptors (color, texture) with deep representations (ResNet, CLIP).  
It highlights how clustering methods can reveal **latent structures** in complex and visual data.  

## 👥 Authors  
- [Ethan Lazimy](https://github.com/EthanLaz)  
- [Titouan Duhazé](https://github.com/titiuo)  
- [Noé Mosca](https://github.com/noe-mosca)  
