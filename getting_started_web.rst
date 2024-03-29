=========================
Getting Started (Website)
=========================


.. contents::
   :depth: 3
..

Understanding the Context for our Task
======================================

Let’s start with a research question we’re interested in. We have a list
of exome variants that we’ve found in our patient population of
interest. Our research question is:

   Given this list of variants, which are potentially pathogenic?

This research question will take us through understanding how the
Open-Cravat annotator works.

Learning Objectives
===================

-  **Create** as user account on the open cravat site
-  **Search** for available annotators on the open cravat site
-  **Upload** and **annotate** variant files on the site
-  **Filter** annotated results for visualization
-  **Visualize** and **Summarize** Results in Open-Cravat
-  **Export** and **Share** annotation results with others

You can click on each box in the diagram below to go to the relevant
section.

.. container:: cell

   .. container:: cell-output-display

      .. container::

         .. container::

            .. image:: getting_started_web_files/figure-rst/mermaid-figure-1.png
               :width: 2.81in
               :height: 5.25in

Creating an Open Cravat Account
===============================

Let’s start out by creating an account on https://run.opencravat.org. If
your organization is running Open-Cravat locally, you will need to find
out the appropriate URL for the instance of Open-Cravat.

Here’s the iniial screen we’ll see when we go to
https://run.opencravat.org. You’ll click on the “Sign Up” Button to
create an account.

|image1| Enter your details in the form, and sign up. You’ll
automatically be signed into the interface and will be ready to go for
the next step.

.. image:: images/oc-signup.png

Browse Annotators
=================

[Video Here]

If we click on the ``STORE`` tab in the top left of the interface, we’ll
see the variety of annotators that are available to us.

.. image:: images/oc-browse-annotators-1.png

Let’s browse the clinically relevant annotators by clicking on the
“Clinically Relevant” checkbox:

.. image:: images/oc-browse-annotators-2.png

As we browse the annotators available to us, we notice two specific
annotators we want to work with. Let’s use two clinically relevant
annotators: `CiViC <https://civicdb.org/welcome>`__ (Clinical
Interpretations of Variants in Cancer) and
`ClinVar <https://www.ncbi.nlm.nih.gov/clinvar/>`__, a public archive of
interpretations of clinically relevant patients.

To get more information, click on the box with the CiViC:

|image2| And you’ll see more information about the annotator:

.. image:: images/oc-browse-annotators-4-civic.png

Now we know which annotators we want to use, so let’s annotate a file.

Convert to Input File Format
============================

Open-Cravat supports VCF files for input, but also has a simplified
format to be used for input files.

We’ll use an exome example and annotate it. Let’s take a look at the
first few lines of this file to understand the input format.

::

   chr1    946247  G   A
   chr1    952421  A   G
   chr1    953259  T   C
   chr1    953279  T   C
   chr1    961945  G   C
   chr1    965125  G   C
   chr1    965338  TTAT    -
   chr1    965667  CC  -
   chr1    973858  G   C

This format contains the following columns: ``chromosome``,
``position``, ``reference``, and ``allele``.

Much more information about the supported file formats are here: `File
Formats <https://open-cravat.readthedocs.io/en/latest/File-Formats.html>`__.

Submit Annotation Job
=====================

[video here]

Before we move on, let’s take a look at the overall workflow for
annotating in the GUI. We’ll start out by 1) submitting our input file,
2) selecting the annotators, and then 3) submitting our job.

.. image:: images/oc-gui-workflow.png

Let’s start the workflow. We can now add our variant file to annotate
and submit a job. Select the ``JOBS`` tab in the top left corner of the
interface.

.. image:: images/oc-jobs.png

Our exome file corresponds to the ``hg19/GRCH37`` build, so make sure
that this genome is selected under the Genome field

.. image:: images/oc-jobs-genome.png

Now we’ll add our input file. Add your ``Pedja_exome.tsv`` file here by
clicking the “ADD INPUT FILES” button:

.. image:: images/oc-jobs-input.png

Now we can select our annotators. Under annotations in the box below
“Variants”, click on the “Clinical Relevance” category.

.. image:: images/oc-jobs-category.png

Select the ``CiViC`` (not ``CiViC Gene``) and ``ClinVar`` annotation
checkboxes.

.. image:: images/oc-jobs-annotators.png

Now we’re ready to annotate. Click the ``ANNOTATE`` button at the bottom
of the webpage. Now you’ve submitted your job.

.. image:: images/oc-jobs-submit.png

Depending on the size of your Variant file, it may take time for your
job to finish. You’ll see the job running in the table on the right of
the interface.

Filter Results
==============

[Video here]

   We are interested in those variants that are associated with Breast
   Cancer in ClinVar. How do we find those?

Now we take a look at our results in the web interface. Under the list
of jobs, we can see our job. Let’s select ``Open Result Viewer`` under
the **Status** tab:

|image3| Keep in mind that the web interface is limited to visualizing
100,000 variants, so if you have a larger result file, you’ll need to
filter the results down. So let’s take a look at how to filter our
variants down.

We can filter variants by selecting the Filter tab in the Results
viewer:

.. image:: images/oc-filter-select-tab.png

Under “Variant Properties” we can limit our list of variants to those
that have ClinVar annotations. Let’s build a filter using the Query
Builder, which will allow us to impose multiple criteria as a filter.

.. image:: images/oc-filter-query-builder.png

We’ll add a rule (a logical condition) to our filter using the ``+``
button:

.. image:: images/oc-filter-add-rule.png

Now we’ll add a rule and select those that have ``ClinVar`` annotations.
To do this, we’ll first select ``ClinVar`` on the left, the
``Clinical Significance`` column, and ``has data``:

|image4| Now we can apply this rule we’ve built by clicking on the
``Apply Filter`` button on the bottom right of the Query Builder:

|image5| How many variants are left after the filtering?

Visualize Results
=================

[Video here]

Now that we’ve filtered, let’s go back to the Summary Tab:

|image6| In the Visualize tab, we can see information about the
annotated variants, such as from the sequence ontology. We can get the
counts within a sequence ontology category by mousing over that category
in our plot:

|image7| Using the save icon, you can also save these visualizations.

Let’s move over to the **Variant** tab and look for pathogenic variants.
First, we’ll click over to the **Variant** tab:

|image8| Scrolling to the right, we can see there is a column for the
ClinVar annotations. Notice the **+** on the top right. We’ll click that
to expand the ClinVar annotations:

|image9| In the **Clinical Significance** column, we can see that we can
filter. Let’s select those variants that have **pathogenic**
significance. Clicking into the search box underneath this column, we
can select **pathogenic**:

.. image:: images/oc-visualize-pathogenic.png

How many variants are pathogenic?

What you learned
================

You learned a lot in this section. You learned how to:

-  Create a User Account
-  Browse Open-Cravat’s store to look for annotators
-  Submit a job to the Open-Cravat server
-  Filter results in the Results Viewer
-  Visualize results in the Results Viewer

.. |image1| image:: images/oc-first.png
.. |image2| image:: images/oc-browse-annotators-3.png
.. |image3| image:: images/oc-filter-job.png
.. |image4| image:: images/oc-filter-create.png
.. |image5| image:: images/oc-filter-apply.png
.. |image6| image:: images/oc-visualize-tab.png
.. |image7| image:: images/oc-visualize-seq-ontology.png
.. |image8| image:: images/oc-visualize-variant.png
.. |image9| image:: images/oc-visualize-clinvar.png
