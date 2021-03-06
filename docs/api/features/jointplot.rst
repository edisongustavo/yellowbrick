.. -*- mode: rst -*-

Direct Data Visualization
=========================

Sometimes for feature analysis you simply need a scatter plot to determine the distribution of data. Machine learning operates on high dimensional data, so the number of dimensions has to be filtered. As a result these visualizations are typically used as the base for larger visualizers; however you can also use them to quickly plot data during ML analysis.

Joint Plot Visualization
------------------------

The ``JointPlotVisualizer`` plots a feature against the target and shows the distribution of each via a histogram on each axis.


.. plot::
    :context: close-figs
    :alt: JointPlot

    from yellowbrick.datasets import load_concrete
    from yellowbrick.features import JointPlotVisualizer

    # Load the dataset
    X, y = load_concrete()

    # Instantiate the visualizer
    visualizer = JointPlotVisualizer(columns="cement")

    visualizer.fit_transform(X, y)        # Fit and transform the data
    visualizer.show()                     # Finalize and render the figure


The ``JointPlotVisualizer`` can also be used to compare two features.

.. plot::
    :context: close-figs
    :alt: JointPlot comparing two features

    from yellowbrick.datasets import load_concrete
    from yellowbrick.features import JointPlotVisualizer

    # Load the dataset
    X, y = load_concrete()

    # Instantiate the visualizer
    visualizer = JointPlotVisualizer(columns=["cement", "ash"])

    visualizer.fit_transform(X, y)        # Fit and transform the data
    visualizer.show()                     # Finalize and render the figure


In addition, the ``JointPlotVisualizer`` can be plotted with hexbins in the case
of many, many points.

.. plot::
    :context: close-figs
    :alt: JointPlot

    from yellowbrick.datasets import load_concrete
    from yellowbrick.features import JointPlotVisualizer

    # Load the dataset
    X, y = load_concrete()

    # Instantiate the visualizer
    visualizer = JointPlotVisualizer(columns="cement", kind="hexbin")

    visualizer.fit_transform(X, y)        # Fit and transform the data
    visualizer.show()                     # Finalize and render the figure


API Reference
-------------

.. automodule:: yellowbrick.features.jointplot
    :members: JointPlot
    :undoc-members:
    :show-inheritance:
