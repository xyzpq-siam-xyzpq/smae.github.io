---
title: "Siamese Masked Autoencoders"
author_list: <span class="nowrap"> Anonymous NeurIPS 2023 submission
mathjax: true
---
![SiamMAE model diagram](resources/model.png)


## Abstract

Establishing correspondence between images or scenes is a significant challenge in computer vision, especially given occlusions, viewpoint changes, and varying object appearances. In this paper, we present Siamese Masked Autoencoders (SiamMAE), a simple extension of Masked Autoencoders (MAE) for learning visual correspondence from videos. SiamMAE operates on pairs of randomly sampled video frames and *asymmetrically* masks them. These frames are processed *independently* by an encoder network, and a decoder composed of a sequence of cross-attention layers is tasked with predicting the missing patches in the future frame. By masking a large fraction (95%) of patches in the future frame while leaving the past frame unchanged, SiamMAE encourages the network to focus on object motion and learn object-centric representations. Despite its conceptual simplicity, features learned via SiamMAE outperform state-of-the-art self-supervised methods on video object segmentation, pose keypoint propagation, and semantic part propagation tasks. SiamMAE achieves competitive results without relying on data augmentation, handcrafted tracking-based pretext tasks, or other techniques to prevent representational collapse.

---

## Qualitative results

### DAVIS: Video Object Segmentation 
<div style="text-align: center">
	<video class="results_video_256" playsinline autoplay muted loop>
		  <source src="resources/davis/blackswan.mp4" type='video/mp4'>
		  <!-- <source src="resources/bair/bair_indiv_0_sfri.mp4" type='video/mp4'> -->
		  <source src="resources/davis/blackswan.webm" type='video/webm'>
		  Your browser does not support the video tag.
	</video>	
	<video class="results_video_256" playsinline autoplay muted loop>
		  <source src="resources/davis/breakdance.mp4" type='video/mp4'>
		  <!-- <source src="resources/bair/bair_indiv_0_sfri.mp4" type='video/mp4'> -->
		  <source src="resources/davis/breakdance.webm" type='video/webm'>
		  Your browser does not support the video tag.
	</video>
	<video class="results_video_256" playsinline autoplay muted loop>
		  <source src="resources/davis/libby.mp4" type='video/mp4'>
		  <!-- <source src="resources/bair/bair_indiv_0_sfri.mp4" type='video/mp4'> -->
		  <source src="resources/davis/libby.webm" type='video/webm'>
		  Your browser does not support the video tag.
	</video>
	<video class="results_video_256" playsinline autoplay muted loop>
		  <source src="resources/davis/horsejump-high.mp4" type='video/mp4'>
		  <!-- <source src="resources/bair/bair_indiv_0_sfri.mp4" type='video/mp4'> -->
		  <source src="resources/davis/horsejump-high.webm" type='video/webm'>
		  Your browser does not support the video tag.
	</video>
	<video class="results_video_256" playsinline autoplay muted loop>
		  <source src="resources/davis/lab-coat.mp4" type='video/mp4'>
		  <!-- <source src="resources/bair/bair_indiv_0_sfri.mp4" type='video/mp4'> -->
		  <source src="resources/davis/lab-coat.webm" type='video/webm'>
		  Your browser does not support the video tag.
	</video>
	<video class="results_video_256" playsinline autoplay muted loop>
		  <source src="resources/davis/parkour.mp4" type='video/mp4'>
		  <!-- <source src="resources/bair/bair_indiv_0_sfri.mp4" type='video/mp4'> -->
		  <source src="resources/davis/parkour.webm" type='video/webm'>
		  Your browser does not support the video tag.
	</video>
</div>

---
### VIP: Semantic Part Propagation (shown at 5FPS)
<div style="text-align: center">
	<video class="results_video_256" playsinline autoplay muted loop>
		  <source src="resources/VIP/videos37.mp4" type='video/mp4'>
		  <!-- <source src="resources/bair/bair_indiv_0_sfri.mp4" type='video/mp4'> -->
		  <source src="resources/VIP/videos37.webm" type='video/webm'>
		  Your browser does not support the video tag.
	</video>	
	<video class="results_video_256" playsinline autoplay muted loop>
		  <source src="resources/VIP/videos91.mp4" type='video/mp4'>
		  <!-- <source src="resources/bair/bair_indiv_0_sfri.mp4" type='video/mp4'> -->
		  <source src="resources/VIP/videos91.webm" type='video/webm'>
		  Your browser does not support the video tag.
	</video>
	<video class="results_video_256" playsinline autoplay muted loop>
		  <source src="resources/VIP/videos151.mp4" type='video/mp4'>
		  <!-- <source src="resources/bair/bair_indiv_0_sfri.mp4" type='video/mp4'> -->
		  <source src="resources/VIP/videos151.webm" type='video/webm'>
		  Your browser does not support the video tag.
	</video>
	<video class="results_video_256" playsinline autoplay muted loop>
		  <source src="resources/VIP/videos198.mp4" type='video/mp4'>
		  <!-- <source src="resources/bair/bair_indiv_0_sfri.mp4" type='video/mp4'> -->
		  <source src="resources/VIP/videos198.webm" type='video/webm'>
		  Your browser does not support the video tag.
	</video>
	<video class="results_video_256" playsinline autoplay muted loop>
		  <source src="resources/VIP/videos297.mp4" type='video/mp4'>
		  <!-- <source src="resources/bair/bair_indiv_0_sfri.mp4" type='video/mp4'> -->
		  <source src="resources/VIP/videos297.webm" type='video/webm'>
		  Your browser does not support the video tag.
	</video>
	<video class="results_video_256" playsinline autoplay muted loop>
		  <source src="resources/VIP/videos361.mp4" type='video/mp4'>
		  <!-- <source src="resources/bair/bair_indiv_0_sfri.mp4" type='video/mp4'> -->
		  <source src="resources/VIP/videos361.webm" type='video/webm'>
		  Your browser does not support the video tag.
	</video>
</div>

### JHMDB: Pose Keypoint Propagation
<div style="text-align: center">
	<video class="results_video_256" playsinline autoplay muted loop>
		  <source src="resources/jhmdb/1.mp4" type='video/mp4'>
		  <!-- <source src="resources/bair/bair_indiv_0_sfri.mp4" type='video/mp4'> -->
		  <source src="resources/jhmdb/1.webm" type='video/webm'>
		  Your browser does not support the video tag.
	</video>	
	<video class="results_video_256" playsinline autoplay muted loop>
		  <source src="resources/jhmdb/2.mp4" type='video/mp4'>
		  <!-- <source src="resources/bair/bair_indiv_0_sfri.mp4" type='video/mp4'> -->
		  <source src="resources/jhmdb/2.webm" type='video/webm'>
		  Your browser does not support the video tag.
	</video>
	<video class="results_video_256" playsinline autoplay muted loop>
		  <source src="resources/jhmdb/3.mp4" type='video/mp4'>
		  <!-- <source src="resources/bair/bair_indiv_0_sfri.mp4" type='video/mp4'> -->
		  <source src="resources/jhmdb/3.webm" type='video/webm'>
		  Your browser does not support the video tag.
	</video>
	<video class="results_video_256" playsinline autoplay muted loop>
		  <source src="resources/jhmdb/4.mp4" type='video/mp4'>
		  <!-- <source src="resources/bair/bair_indiv_0_sfri.mp4" type='video/mp4'> -->
		  <source src="resources/jhmdb/4.webm" type='video/webm'>
		  Your browser does not support the video tag.
	</video>
	<video class="results_video_256" playsinline autoplay muted loop>
		  <source src="resources/jhmdb/5.mp4" type='video/mp4'>
		  <!-- <source src="resources/bair/bair_indiv_0_sfri.mp4" type='video/mp4'> -->
		  <source src="resources/jhmdb/5.webm" type='video/webm'>
		  Your browser does not support the video tag.
	</video>
	<video class="results_video_256" playsinline autoplay muted loop>
		  <source src="resources/jhmdb/6.mp4" type='video/mp4'>
		  <!-- <source src="resources/bair/bair_indiv_0_sfri.mp4" type='video/mp4'> -->
		  <source src="resources/jhmdb/6.webm" type='video/webm'>
		  Your browser does not support the video tag.
	</video>
</div>