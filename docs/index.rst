.. automodule:: tes

.. _manual-main:

======
py-tes
======

.. image:: https://img.shields.io/github/actions/workflow/status/ohsu-comp-bio/py-tes/tests.yml?logo=github
   :alt: GitHub Actions Test Status
   :target: https://github.com/ohsu-comp-bio/py-tes/actions
.. image:: https://coveralls.io/repos/github/ohsu-comp-bio/py-tes/badge.svg?branch=master
   :target: https://coveralls.io/github/ohsu-comp-bio/py-tes?branch=master
.. image:: https://img.shields.io/badge/License-MIT-yellow.svg
   :target: https://opensource.org/licenses/MIT

*py-tes* is a library for interacting with servers implementing the
`GA4GH Task Execution
Schema <https://github.com/ga4gh/task-execution-schemas>`__.

Install
~~~~~~~

Available on `PyPI <https://pypi.org/project/py-tes/>`__.

::

   pip install py-tes

Example
~~~~~~~

::

   import tes

   task = tes.Task(
       executors=[
           tes.Executor(
               image="alpine",
               command=["echo", "hello"]
           )
       ]
   )

   cli = tes.HTTPClient("http://funnel.example.com", timeout=5)
   task_id = cli.create_task(task)
   res = cli.get_task(task_id)
   cli.cancel_task(task_id)


.. _main-support:

-------
Support
-------

* For releases, see :ref:`Changelog <changelog>`.
* Check :ref:`frequently asked questions (FAQ) <project_info-faq>`.
* For **bugs and feature requests**, please use the `issue tracker <https://github.com/ohsu-comp-bio/tes/issues>`_.
* For **contributions**, visit py-tes on `Github <https://github.com/ohsu-comp-bio/tes>`_ and read the :ref:`guidelines <project_info-contributing>`.

.. _main-resources:

---------
Resources
---------

`Snakemake <https://snakemake.github.io/>`_
    The Snakemape workflow management system is a tool to create reproducible and scalable data analyses

`Nextflow <https://www.nextflow.io/>`_
    Nextflow enables scalable and reproducible scientific workflows using software containers. It allows the adaptation of pipelines written in the most common scripting languages. 

`Funnel <https://ohsu-comp-bio.github.io/funnel/>`_
    Funnel is a toolkit for distributed task execution with a simple API.

`cwl-tes <https://github.com/ohsu-comp-bio/cwl-tes>`_
    cwl-tes submits your tasks to a TES server. Task submission is parallelized when possible. 

`ga4gh-tes <https://github.com/microsoft/ga4gh-tes>`_
    C# implementation of the GA4GH TES API; provides distributed batch task execution on Microsoft Azure 

.. toctree::
   :caption: API
   :name: api
   :hidden:
   :maxdepth: 1

   api/tes
