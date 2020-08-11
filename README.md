# Probabilistic Linear Discriminant Analysis

__Disclaimers__

1. This model was written for
 an [Explainable Artificial Intelligence (XAI) project](
     http://shaftolab.com/people.html), 
 so it stores a bunch of parameters in memory that 
 are not necessary for simple classification problems.
2. The model parameters are estimated via empirical Bayes.

__Paper Citation__

[Ioffe S. (2006) Probabilistic Linear Discriminant Analysis. 
 In: Leonardis A., Bischof H., Pinz A. (eds) Computer Vision – ECCV 2006. 
 ECCV 2006.](
 https://link.springer.com/chapter/10.1007/11744085_41)

__Dependencies__

There are three ways You can install dependencies.

1. If you don't use virtual environments:
    `pip install PATH/TO/PARENT/DIRECTORY/plda`.
2. To install within a virtual environment you already created, 
     first activate that environment,
     and then run `pip install PATH/TO/PARENT/DIRECTORY/plda`.
3. If you want to create a Conda environment _and_ 
    install this package into that environment, 
    first navigate your way into the directory containing this 
    `README.md` file.
   Then run the following to create a Conda environment named "plda".

    ``` shell
    conda env create -f environment.yml -n plda  # plda is the environment name.
    ```

You get Conda by downloading either [Anaconda or Miniconda](https://docs.conda.io/projects/conda/en/latest/).

For full specification of dependencies, see [environment.yml](./environment.yml).

__Usage__
1. If you installed this package in a virtual environment, 
    activate that environment first.
2. Add `import plda` to your code.
3. See MNIST demo below for examples of things you can do with this package.

## Demo with MNIST Handwritten Digits Data
Outline for [mnist_demo/mnist_demo.ipynb](./mnist_demo/mnist_demo.ipynb).

1. Import plda and other convenient packages.
2. Load data.
3. Preprocess data.
4. Fit model.
5. __How to classify datapoints: Overfit classifier__.
6. __How to classify datapoints: Better-fit classifier__.
7. Extracting LDA-features.
8. __How to classify datapoints: "same-or-different category" discrimination__.
9. Extracting preprocessing information.
10. Extracting model parameters.

## Testing

If you installed this package in an environment, activate it.
For example, if you created the Conda environment with the name `plda`, 
 activate it with the following.
``` shell
conda activate plda  # If `plda` is the name you gave the Conda environment.
```

To run all tests (~120 seconds with ~60 CPU cores), use the following.
``` shell
pytest plda/  # README.md should be in this directory.
```

To run a particular test file, run one of the following.
``` shell
pytest plda/tests/test_model/test_model_units.py  # ~.66s for me.
pytest plda/tests/test_model/test_model_integration.py  # ~1.0s for me.
pytest plda/tests/test_model/test_model_inference.py  #  ~80.6s for me.

pytest plda/tests/test_optimizer/test_optimizer_units.py  # ~.59s for me.
pytest plda/tests/test_optimizer/test_optimizer_integration.py  # ~.78s.
pytest plda/tests/test_optimizer/test_optimizer_inference.py  # ~25.3s for me.

pytest plda/tests/test_classifier/test_classifier_integration.py  # ~.69s.
```

Once you finish running the tests, 
 remove all the `__pycache__/` folders generated by pytest with the following.
``` shell
py3clean plda/*  # This README.md should be in here.
```

Finally, if you are done working with the model and test code, 
 deactivate the Conda environment.
``` shell
conda deactivate  # You can run this from any directory.
```
