# Open_source_SW_Final



### ๐คทโ What I do my project
- In this final-project, I use Python's *Scikit-learn* package.
- Based on training data on tumor data set, I find the best model and hyperparameters that have the highest accuracy of testing data.

-------------

### ๐งพ The training dataset
##### brain Tumor
- Brain Tumors are classified as: Benign Tumor, Malignant Tumor, Pituitary Tumor, etc.
- The folder contains MRI data.
- The images are split into Training and Testing folders.
- Each folder has more four subfolders. 
- These folders have MRIs of respective tumor classes

-------------

### ๐ The algorithm I choose 
- I choose the gaussian process algorithm.

<pre>
<code>
sklearn.gaussian_process.GaussianProcessClassifier(kernel=None, *, optimizer='fmin_l_bfgs_b', n_restarts_optimizer=0, max_iter_predict=100, warm_start=False, copy_X_train=True, random_state=None, multi_class='one_vs_rest', n_jobs=None)
</code>
</pre>

- Gaussian Processes (GP) are a generic supervised learning method designed to solve regression and probabilistic classification problems.
- The advantages of Gaussian processes are:
  * The prediction interpolates the observations (at least for regular kernels).
  * The prediction is probabilistic (Gaussian) so that one can compute empirical confidence intervals and decide based on those if one should refit (online fitting, adaptive fitting) the prediction in some region of interest.
  * Versatile: different kernels can be specified. Common kernels are provided, but it is also possible to specify custom kernels.

- The disadvantages of Gaussian processes include:
  * They are not sparse, i.e., they use the whole samples/features information to perform the prediction.
  * They lose efficiency in high dimensional spaces โ namely when the number of features exceeds a few dozens.
  
-------------  

### ๐ป Hyper-parameter of the function
- kernel
  * kernel instance, default=None
  * The kernel specifying the covariance function of the GP. If None is passed, the kernel โ1.0 * RBF(1.0)โ is used as default.
  * Note that the kernelโs hyperparameters are optimized during fitting. Also kernel cannot be a *CompoundKernel*.

- optimizer
  * โfmin_l_bfgs_bโ, callable or None, default=โfmin_l_bfgs_bโ
  * Can either be one of the internally supported optimizers for optimizing the kernelโs parameters, specified by a string, or an externally defined optimizer passed as a callable.
  * Per default, the โL-BFGS-Bโ algorithm from scipy.optimize.minimize is used. If None is passed, the kernelโs parameters are kept fixed.
  
- n_restarts_optimizer
  * int, default=0
  * The number of restarts of the optimizer for finding the kernelโs parameters which maximize the log-marginal likelihood.
  * n_restarts_optimizer=0 implies that one run is performed.
  
- max_iter_predict
  * int, default=100
  * The maximum number of iterations in Newtonโs method for approximating the posterior during predict. 
  * Smaller values will reduce computation time at the cost of worse results.
  
- warm_start
  * bool, default=False
  * This can speed up convergence when _posterior_mode is called several times on similar problems as in hyperparameter optimization.
  
- copy_X_train
  * bool, default=True
  * If True, a persistent copy of the training data is stored in the object.
  * Otherwise, just a reference to the training data is stored, which might cause predictions to change if the data is modified externally.
  
- random_state
  * int, RandomState instance or None, default=None
  * Determines random number generation used to initialize the centers
  
- multi_class
  * multi_class{โone_vs_restโ, โone_vs_oneโ}, default=โone_vs_restโ
  * Specifies how multi-class classification problems are handled.
  * In โone_vs_restโ, one binary Gaussian process classifier is fitted for each class, which is trained to separate this class from the rest. 
  * In โone_vs_oneโ, one binary Gaussian process classifier is fitted for each pair of classes, which is trained to separate these two classes.
  
- n_jobs
  * int, default=None
  * The number of jobs to use for the computation: the specified multiclass problems are computed in parallel. 
  * 'None' means 1 unless in a *joblib.parallel_backend* context.
  * '-1' means using all processors.
  
-------------

### ๐ Copyright and licensing information
- MIT License
- https://scikit-learn.org/stable/modules/generated/sklearn.gaussian_process.GaussianProcessClassifier.html

-------------

### ๐ Contact information for the distributor or author
- Name : ๊นํ์ (Hyeonseo-Kim)
- Student Number : 20213608
- major : Applied Statistics
- E-mail : khs6101kr@cau.ac.kr
