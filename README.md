# MIT Course 18.065/18.0651, Spring 2023

This is a repository for the course [18.065: Matrix Methods in Data Analysis, Signal Processing, and Machine Learning](http://student.mit.edu/catalog/m18a.html#18.065) at MIT in Spring 2023.   See also [18.065 from spring 2018](https://ocw.mit.edu/courses/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/) (MIT OpenCourseWare) for a previous version of this class.

**Instructor**: [Prof. Steven G. Johnson](http://math.mit.edu/~stevenj).

**Lectures**: MWF1 in 2-190. Handwritten [notes are posted](https://www.dropbox.com/s/zny0l2njkhe5a8c/18.065%20Spring%202023.pdf?dl=0), along with [video recordings (MIT only)](https://canvas.mit.edu/courses/18680/external_tools/595).

**Office hours (virtual):** Thursdays at 4pm [via Zoom](https://mit.zoom.us/j/95322064681?pwd=ZzB3eHllMXpuWnNqc0NaeXZvUXF2dz09).

**Textbook**: [*Linear Algebra and Learning from Data*](https://math.mit.edu/~gs/learningfromdata/) by Gilbert Strang (2019).  (Additional readings will be posted in lecture summaries below.)

**Resources**: [Piazza discussion forum](https://piazza.com/mit/spring2023/18065), [pset partners](https://psetpartners.mit.edu/).

**Grading**: 50% homework, 50% final project.

**Homework**: Biweekly, due Fridays (2/17, 3/3, 3/17, 4/7, 4/21, 5/5) [on Canvas](https://canvas.mit.edu/courses/18680).  You may consult with other students or any other resources you want, but must write up your solutions *on your own*.

**Exams**: None.

**Final project**: Due **May 15** [on Canvas](https://canvas.mit.edu/courses/18680).  You can work in **groups of 1–3** ([sign up on Canvas](https://community.canvaslms.com/t5/Student-Guide/How-do-I-join-a-group-as-a-student/ta-p/468)).
* **1-page** proposal **due Monday April 3** [on Canvas](https://canvas.mit.edu/courses/18680) (right after spring break), but you are encouraged to discuss it with Prof. Johnson earlier to get feedback.
* Pick a problem involving "learning from data" (in the style of the course, but not *exactly* the same as what's covered in lecture), and take it further: to numerical examples, to applications, to testing one or more solution algorithms.  Must include computations (using any language).
* Final report **due May 15**, as an 8–15 page academic paper in the [style template](https://template-selector.ieee.org/secure/templateSelector/format?publicationTypeId=1&titleId=154&articleId=1) of [IEEE Transactions on Pattern Analysis and Machine Intelligence](https://www.computer.org/csdl/journal/tp).
* Like a good academic paper, you should **thoroughly reference** the published literature (citing both original articles and authoritative reviews/books where appropriate \[rarely web pages\]), tracing the historical development of the ideas and giving the reader pointers on where to go for more information and related work and later refinements, with references cited throughout the text (enough to make it clear what references go with what results). (Note: you may re-use diagrams from other sources, but all such usage must be _explicitly credited_; not doing so is [plagiarism](http://writing.mit.edu/wcc/avoidingplagiarism).) See some [previous topic areas](https://ocw.mit.edu/courses/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/pages/final-project/).

What followes is a *brief* summary of what was covered in each lecture, along with links and suggestions for further reading.  It is
*not* a good substitute for attending lecture, but may provide a
useful study guide.

## Lecture 1 (Feb 6)

* Syllabus (above) and introduction.
* ![18.065 overview diagram](https://ocw.mit.edu/courses/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/d6b9603509fe7de36c57a0ed8ebd92d2_chart_300.jpg)
* Column space, basis, rank, rank-1 matrices, A=CR, and AB=∑(col)(row)
* See handwritten notes and lecture video linked above.

**Further reading**: Textbook 1.1–1.3. [OCW lecture 1](https://ocw.mit.edu/courses/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/resources/lecture-1-the-column-space-of-a-contains-all-vectors-ax/)


## Lecture 2 (Feb 8)

* Matrix multiplication by blocks and columns-times-rows.  Complexity: standard algorithm for (m×p)⋅(p×n) is [Θ(mnp): roughly proportional](https://en.wikipedia.org/wiki/Big_O_notation) to mnp for large m,n,p, regardless of how we rearrange it into blocks. (There also [exist theoretically better](https://en.wikipedia.org/wiki/Computational_complexity_of_matrix_multiplication), but highly impractical, algorithms.)
* Briefly reviewed the "famous four" matrix factorizations: [LU](https://en.wikipedia.org/wiki/LU_decomposition), [diagonalization XΛX⁻¹ or QΛQᵀ](https://en.wikipedia.org/wiki/Eigendecomposition_of_a_matrix), [QR](https://en.wikipedia.org/wiki/QR_decomposition), and the [SVD UΣVᵀ](https://en.wikipedia.org/wiki/Singular_value_decomposition).  QR and QΛQᵀ in the columns-times-rows picture, especially QΛQᵀ (diagonalization for real A=Aᵀ) as a sum of symmetric rank-1 projections.
* The [four fundamental subspaces](https://web.mit.edu/18.06/www/Essays/newpaper_ver3.pdf) for an m×n matrix A of rank r, mapping "inputs" x∈ℝⁿ to "outputs" Ax∈ℝᵐ: the "input" subspaces C(Aᵀ) (row space, dimension r) and its [orthogonal complement](https://en.wikipedia.org/wiki/Orthogonal_complement) N(A) (nullspace, dimension n–r); and the "output" subspaces C(A) (column space, dimension r) and its orthogonal complement N(Aᵀ) (left nullspace, dimension m–r).

**Further reading**: Textbook 1.3–1.6. [OCW lecture 2](https://ocw.mit.edu/courses/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/resources/lecture-2-multiplying-and-factoring-matrices/).  If you haven't seen [matrix multiplication by blocks](https://www.math.ucdavis.edu/~linear/old/notes9.pdf) before, [here is a nice video](https://www.youtube.com/watch?v=KCUgWj5nhYc).

## *Optional* Julia Tutorial: Wed Feb 8 @ 5pm via Zoom

* Virtually via Zoom.  See [the recording](https://mit.zoom.us/rec/share/n2B1-t0NoGd5pr9gNBLgDYme159TstNttH5PLMcYPsEFEThCohKIJPsLrZXRhaZZ.LMM65H-ATiUFXkPf?startTime=1675893372000) (MIT only).

A basic overview of the Julia programming environment for numerical computations that we will use in 18.06 for simple computational exploration.   This (Zoom-based) tutorial will cover what Julia is and the basics of interaction, scalar/vector/matrix arithmetic, and plotting — we'll be using it as just a "fancy calculator" and no "real programming" will be required.

* [Tutorial materials](https://github.com/mitmath/julia-mit) (and links to other resources)

If possible, try to install Julia on your laptop beforehand using the instructions at the above link.  Failing that, you can run Julia in the cloud (see instructions above).
