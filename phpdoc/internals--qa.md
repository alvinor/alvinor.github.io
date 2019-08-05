## Quality Assurance

To continuously improve on the stability of phpDocumentor we make use of Wercker and Scrutinizer to verify and inspect the source code.

Using Wercker we are able to run all automated tests, such as PHPUnit and Behat, and verify if the application still behaves as expected. The code coverage that is collected during the running of PHPUnit is sent to Scrutinizer, which will create statistics out of it.

Scrutinizer is a service that runs static analysis tools and extracts valuable information that can be used to improve the application. The page for phpDocumentor is located at https://scrutinizer-ci.com/g/phpDocumentor/phpDocumentor2.

The following aspects of the application are inspected:

1. Code Coverage
1. Overall quality
1. Coding Standards violations
1. Mess detection
1. Security advisories
1. Copy/paste detection
1. Metrics

and much more.

The best location to start looking for parts to improve is on the Issues page; there you will find all things that Scrutinizer detected to be wrong with the project.