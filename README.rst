Slides-and-book theme
#####################

This is a theme for Sphinx_ and Hieroglyph_,
for making a document available as a

* a set of browsable HTML pages (with the ``html`` builder),
* an HTML slideshow (with the ``slides`` builder),
* a printer-friendly single HTML page (with the ``singlehtml`` builder).

.. _Sphinx: http://sphinx-doc.org/
.. _Hieroglyph: http://hieroglyph.io/

How to use it
+++++++++++++

This tutorial assumes that your sphinx project has
a separate ``source`` directory.
Adaptation is required if your source files are in the project root.

#. create a ``themes`` directory in your sphinx project,
   you must clone this repository
   under the ``themes`` directory of yoursphinx project;

#. in the HTML section of the ``conf.py`` file, set the following variables::

     html_theme_path = ["../themes"]
     html_theme = "sphinx-sab-theme"

#. in the Hieroglyph section of the ``conf.py`` file,
   set the following varables::

     slide_theme_options = {'custom_css': '../../_static/sab-slides.css'}

   NB: the path above aims to point at ``build/html/_static/sab-slides.css``,
   assuming that slides are generated in ``build/html/slides``,
   which is the configuration we recommend.
   If slides are generated in a directory separate from the HTML pages,
   the path of ``sab-slides.css`` should be adapted accordingly.

#. Important: **do not** set ``slide_theme`` to ``sphinx-sab-theme``.
   For the moment,
   this theme is grafting itself to the standard hieroglyph themes
   using the ``custom_css`` option.
   This may change in the future.

#. The top-level document (usually ``source/index.rst``) should contain
   the following directive::

     .. rst-class:: sab-printable

   *before* its title.
   This ensures that the single-paged version is printer friendly.
   

Customizing the theme
+++++++++++++++++++++

You may add a file named ``sab-custom.css`` in your ``_static`` directory.
This file will be automatically imported in all versions
(standard, HTML, single-paged).
