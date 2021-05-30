# jmeter_1

# jmeter with TPS 1.

Pre-requisite for running tests - Start the end-point at 'http://localhost:8080/swagger-ui.html'
Jmeter should be installed OR docker pull justb4/jmeter
then docker images to confirm

Run the below jmeter test plan from Jenkins command-line CI-

jmeter -n -t GetTopResultsApi.jmx -l GetTopWcResult_Report.jtl -e -o GetTopWcResult_Report

The results with TPS (Hits per second) of 1 would be displayed in GetTopWcResult_Report folder within index.html charts.

->docker tag justb4/jmeter jmeter

To run the .jmx file with docker image -
-> docker run jmeter -n -t GetTopResultsApi.jmx -l GetTopWcResult_dockerReport.jtl -e -o GetTopWcResult_dockerReport

prior to this the jmeter image should be copied to "/opt/apache-jmeter-5.3/" where the docker pull command is done.