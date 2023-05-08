Download Link: https://assignmentchef.com/product/solved-statsm232a-project-1-statistics-of-natural-images
<br>
<strong>project 1: Statistics of Natural Images</strong>

This is a small project aiming at verifying some properties of natural image statistics that we discussed in Chapter 2. You can use any programming languages.

Attached are four natural images (two from urban and two from countryside scenes).

<strong>What to hand in: </strong>Submit a report on the CCLE site. Your score will be based on the quality of your results and the analysis (diagnostics of issues and comparisons) of these results in your report. Please also submit a zip file including your code,  and make sure your code is consistent with results in report.

<strong>Problem 1 </strong>(High kurtosis and scale invariance, 3 points). For computational considerations, first convert image to grey level and re-scale the intensity to [0,31] i.e. 32 grey levels. Convolve the images with a gradient filter r<em>xI</em>, i.e. the intensity di↵erence between two adjacent (horizontally or vertically). You can either pick any single image for the following steps or accumulate the histograms (average) over the 4 images.

<ol>

 <li>Plot the histogram <em>H</em>(<em>z</em>) for the di↵erence against the horizontal axis <em>z </em>2 [ 31<em>,</em>+31]. Then do a log-plot log<em>H</em>(<em>z</em>). [Some bins will be zero, you can assign <em>&#x270f; </em>for such bins in the log-plot].</li>

 <li>Compute the mean, variance, and kurtosis for this histogram [Report the numericnumbers in your report].</li>

 <li>Fit this histogram to a Generalized Gaussian distribution <em>e</em>|<em><sup>z/ </sup></em>| and plot the fittedcurves super-imposed against the histogram. What is the value of in the fitted generalized Gaussian?</li>

 <li>Plot the Gaussian distribution using the mean and the variance above, and superimpose this plot with the plots in step (1) above (i.e. plot the Gaussian and its log plot, this is easy to do in matlab).</li>

 <li>Down-sample your image(s) by a 2 ⇥ 2 average (or simply sub-sample) the image. Plot the histogram and log histogram, and impose with the plots in step 1, to compare the di↵erence. Repeat this down-sampling process 2-3 times.</li>

 <li>Synthesize a uniform noise image, i.e. each pixel is drawn independently from auniform number in [0<em>,</em>31]. Repeat 1-2-4 to compare the di↵erence between a noise image and a natural image. Do a 2 ⇥ 2 average instead of sub-sampling.</li>

</ol>

1

<strong>Problem 2</strong>. (Verify the 1/f power law observation in natural images, 3 points).

Do an FFT (Fast Fourier Transform) on the grey image <em>I </em>which returns a Fourier image <sup>ˆ</sup>(<em>⇠,⌘</em>) which is complex number matrix indexed by (<em>⇠,⌘</em>) for its horizontal and vertical frequencies. Compute the amplitude (modulus) of each complex number <em>A</em>(<em>⇠,⌘</em>).

Denote the frequency <em>f </em>= p<em>⇠</em><sup>2 </sup>+ <em>⌘</em><sup>2</sup>, and transfer to a polar coordinate, and we calculate the total Fourier power <em>A</em><sup>2</sup>(<em>f</em>) for each frequency (i.e. you need to discretize <em>f</em>, and calculate the <em>A</em><sup>2</sup>(<em>f</em>) averaged over the ring for each <em>f</em>, stop <em>f </em>when the circle hits the boundary of the Fourier image).

<ol>

 <li>Plot log<em>A</em>(<em>f</em>) against log<em>f</em>. This should be close to a straight line for each image.</li>

</ol>

Plot the curves for the 4 images in one figure for comparison.

<ol start="2">

 <li>Compute the integration (summation in discrete case) of <em>S</em>(<em>f</em><sub>0</sub>) = R⌦ <em>A</em><sup>2</sup>(<em>⇠,⌘</em>)<em>d⇠d⌘ </em>over the domain</li>

</ol>

⌦(<em>f</em><sub>0</sub>) = {(<em>⇠,⌘</em>) : <em>f</em><sub>0 </sub>q<em>⇠</em><sup>2 </sup>+ <em>⌘</em><sup>2 </sup> 2<em>f</em><sub>0</sub>}

Plot <em>S</em>(<em>f</em><sub>0</sub>) over <em>f</em><sub>0</sub>, the plot should fit to a horizontal line (with fluctuation) as <em>S</em>(<em>f</em><sub>0</sub>) is supposed to be a constant over <em>f</em><sub>0</sub>.

<strong>Problem 3</strong>. (A 2D scale invariant world, 3 points). Suppose we simulate a toy 2D world where the images consist of only 1D line segments. In an image, a line segment is represented by its center (<em>x<sub>i</sub>,y<sub>i</sub></em>), orientation <em>✓<sub>i </sub></em>and length <em>r<sub>i</sub></em>. The line segments are independently distributed with uniform probability for their centers and orientations. The length follows a probability <em>p</em>(<em>r</em>) / <a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a><a href="#_ftn2" name="_ftnref2"><sup>[2]</sup></a><em>/r</em><a href="#_ftn3" name="_ftnref3"><sup>[3]</sup></a>, i.e. a cubic power law. You may control the density of line by a Poisson distribution. That is, in each unit area, the number of line segments has a certain constant mean. [Hint: How to sample <em>r </em>from <em>p</em>(<em>r</em>)? Calculate the Cumulative Distribution function of <em>p</em>(<em>r</em>), then draw a random number in [0,1].]

<a href="#_ftnref1" name="_ftn1">[1]</a> . Simulate 1 image <em>I</em><sub>1 </sub>of size 1024 ⇥ 1024 pixels with a total <em>N </em>lines. (You need to record all the <em>N </em>lines whose centers are within a range of the image, truncate long lines and hide (discard) lines shorter than a pixel.)

<a href="#_ftnref2" name="_ftn2">[2]</a> . Simulate 2 new images <em>I</em><sub>2 </sub>and <em>I</em><sub>3 </sub>of size 512⇥512 and 256⇥256 pixels respectively. <em>I</em><sub>2 </sub>and <em>I</em><sub>3 </sub>are down-sampled version of <em>I</em><sub>1 </sub>and are generated by shortening the <em>N </em>line segments in <em>I</em><sub>1 </sub>by 50% and 25% respectively (discard lines shorter than 1).

<a href="#_ftnref3" name="_ftn3">[3]</a> . Crop 2 image patches of size 128⇥128 pixels randomly from each of the three images <em>I</em><sub>1</sub><em>,I</em><sub>2</sub><em>,I</em><sub>3 </sub>respectively. Plot these six images [draw the line segments in black on white background].

If you did it right [Please try !], the 6 images must look the same (i.e. you should not be able to tell what scale the 6 images are cropped from). So this 2D world is scale-invariant.