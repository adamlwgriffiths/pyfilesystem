This project is no longer maintained.

PyFileSystem attempts to blend S3 with FileSystem logic and guarantees.

This project broke this.

Instead of treating S3 like a file system, the file system should be treated like S3, a Key-Value store.

That's why we created `Kvstore <https://github.com/chrsbats/kvstore>`_.


====================
Sane S3 PyFileSystem
====================

This fork modifies the S3 implementation of PyFilesystem to be less 'insane'.

The default implementation treats S3 like a filesystem, which requires a lot of fact checking ('is it a directory?', 'does the parent directory exist?').
This fact checking creates a lot of excessive calls which can easily cause your S3 bill to become 100x what it should be (a fact proven through experience).

This fork removes much of this fact checking to make S3FS act more like a KV store and 'just work' rather than enforcing filesystem like behavior and fact checking.

