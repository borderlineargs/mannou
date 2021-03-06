Mannou - Manga Downloader
#########################

|pypi| |pyver| |travis| |docs|

A manga downloader from various sites.

Please remember this package still under development.

This command:

.. code-block:: bash

    $ mannou https://manganelo.com/manga/tomochan_wa_onnanoko --download

will download every chapters to ``~/Manga``

.. contents::


Features
========

* Get info and download every chapters from supported sites.


Installation
============

You must have Python_ and PIP installed in your computer, then:

.. code-block:: bash

    $ pip install mannou

.. _Python: https://www.python.org/


Examples
========

You can use this package as CLI program or import it in your project.


CLI
---

.. code-block:: bash

    $ mannou https://manganelo.com/manga/aiura --download --start 2 --end 3

This command will download manga called *Aiura* from chapter 2 to 3

Project
-------

.. code-block:: python

    >>> import mannou
    >>> url = 'https://manganelo.com/manga/aiura'
    >>> manga = mannou.get(url)
    >>> str(manga) # or manga.title
    Aiura
    >>> manga[0] # or manga.chapters[0]
    Chapter(number='1', url='https://manganelo.com/chapter/aiura/chapter_1')
    >>> images = manga.get_chapter_images(manga[0].url)
    >>> images[0]
    Image(name='1.jpg', url='http://s8.mkklcdn.com/mangakakalot/a1/aiura/chapter_1/1.jpg')
    >>> mannou.download(url, start=1, end=5) # Download every chapters 1 until 5 in 'Aiura' and save it to default location (~/Manga or %USERPROFILE%\Manga)


Documentation
=============

Please refer to https://mannou.readthedocs.io for further documentation.


License
=======
Free software: `GNU General Public License v3`_.

.. _`GNU General Public License v3`: https://github.com/borderlineargs/mannou/blob/master/LICENSE


Credits
=======

* This package use AniList_ api to get manga's info.
* This package structure is heavily influenced by cookiecutter-pypackage_
  and the requests_.

.. _AniList: https://anilist.co/
.. _cookiecutter-pypackage: https://github.com/audreyr/cookiecutter-pypackage
.. _requests: https://github.com/requests/requests


.. |travis| image:: https://img.shields.io/travis/borderlineargs/mannou.svg
    :target: https://travis-ci.org/borderlineargs/mannou
    :alt: Build status of the master branch on linux (Ubuntu Xenial)

.. |pypi| image:: https://img.shields.io/pypi/v/mannou.svg
    :target: https://pypi.org/project/mannou/
    :alt: PyPI

.. |pyver| image:: https://img.shields.io/pypi/pyversions/mannou.svg
    :target: https://pypi.org/project/mannou/
    :alt: Python supported version.

.. |docs| image:: https://readthedocs.org/projects/mannou/badge/
    :target: https://mannou.readthedocs.io/
    :alt: Documentation.
