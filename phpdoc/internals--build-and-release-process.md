## Build and Release process
<note>
Note The process described in this document is not yet fully implemented but is a specification to which the Build and Release process should adhere.
</note>

### Introduction

Releasing phpDocumentor involves a fair amount of actions due to the number of installation options and involved third- parties. This process is completely automated and follows the basic principles of Continuous Delivery where with each commit to the master branch may lead to a new release.
<note>
Note the term ¡®Deployment¡¯ is explicitly avoided given that the Build and Release process is responsible for creating binaries that may be deployed by users and not by ourselves.
</note>

Despite that each commit to master should be releasable it does not mean that every commit should be pushed to the production pear channel.

### Pipeline

1. Commit phase
 - 1. Clone the release-branch into a deployment folder
 - 2. Run a composer install command with the arguments ¨Cno-dev ¨Coptimize-autoloader ¨Cprefer-dist
 - 3. Run Unit tests of the deployment folder
 - 4. Run Behat tests of the deployment folder
2. Analysis phase
  - 1. Run phpCodeSniffer and aggregate results
3. Packaging phase
  - 1. Build PEAR package
  - 2. Build PHAR package
  - 3. Build documentation
  - 4. Store PEAR and PHAR packages in artifact repository
4. Release phase
  - 1. Commit generated artifacts (package.xml) <<< can this be removed??
  - 2. Deploy PEAR package to channel
  - 3. Upload PHAR to phpdoc.org/phpDocumentor.phar
  - 4. Upload PHAR to phpdoc.org/archives/phpDocumentor-[version].phar
  - 5. Create new issue with https://github.com/josegonzalez/homebrew-php using the SHA1 of the phar file and the version number to request an update of the homebrew files (see https://github.com/phpDocumentor/phpDocumentor2/issues/909)
  - 6. Upload documentation to http://www.phpdoc.org/docs/[major].[minor]
  - 7. Set Symlink for latest documentation (http://www.phpdoc.org/docs/latest) to http://www.phpdoc.org/docs/[major].[minor]
5. Announcements
  - 1. Send a mail to the mailing list with the change log contents and title
  - 2. Send a tweet with the new release and a link to the Github release information
  - 3. Update release information on github with:
    - 1. Release title (taken from changelog)
    - 2. Changelog
    - 3. PEAR archive file
    - 4. Phar archive file