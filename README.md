SonataMediaBundle - Media management on steroids
================================================

The ``SonataMediaBundle`` is a media library based on a dedicated ``provider``
which handles different ``type`` of media: files, videos or images.

The online documentation of the bundle is in http://sonata-project.org/bundles/media

For contribution to the documentation you cand find it on [Resources/doc/](https://github.com/sonata-project/SonataMediaBundle/tree/master/Resources/doc)

Each ``type`` is managed by a ``provider`` service which is in charge of:

  - retrieving media metadata
  - generating media thumbnail
  - tweaking the edit form
  - rendering the media

Each ``media`` can be linked to a ``context``. A context can be ``news``,
``user`` or any name you want. A context allows you to group a set of pictures
together. As requirements can be different for each context, a context
is defined by a set of ``formats`` and a set of ``providers``.

As the infrastructure is not standard, the ``MediaBundle`` abstracts the
``filesystem`` layer and the ``cdn`` layer.

The backend is handled by the ``AdminBundle``.


**Google Groups**: For questions and proposals you can post on this google groups

* [Sonata Users](https://groups.google.com/group/sonata-users): Only for user questions
* [Sonata Devs](https://groups.google.com/group/sonata-devs): Only for devs

Available services
------------------

### Providers

    - sonata.media.provider.image         : Image
    - sonata.media.provider.file          : File
    - sonata.media.provider.dailymotion   : Dailymotion
    - sonata.media.provider.vimeo         : Vimeo
    - sonata.media.provider.youtube       : Youtube

### Filesystem

    - sonata.media.filesystem.local       : The local filesystem (default)
    - sonata.media.filesystem.ftp         : FTP
    - sonata.media.filesystem.s3          : Amazon S3
    - sonata.media.filesystem.replicate   : Replicate file to a master and to a slave

### CDN

    - sonata.media.cdn.server             : The local http server (default)
    - sonata.media.cdn.panther            : Panther Portal
    - sonata.media.cdn.fallback           : Fallback, use the fallback (the http server) if the Media is not yet flushed on the CDN

More services will be available in the future depending on your contributions! :)

More information
----------------

You need to go to the Resources/doc folder where the reStructuredText documentation
is available. Please note the Github preview might break and hide some content
(so your best bet is to clone this repository and read the source files locally!).

TODO
----

 - thumbnail synchronisation command line
 - CDN Flush command line