# demo
# SpringBoot + Apache SOLR

This project demonstrate the integration of SPRING Boot with Apache SOLR. 

1. First download the Apache SOLR from http://lucene.apache.org/solr/
		
		Apache Solr is a web application built around Lucene with all kinds of goodies which make the search of the content very easy and quick.

		It adds functionality like

		XML/HTTP and JSON APIs
		Hit highlighting
		Faceted Search and Filtering
		Geospatial Search
		Fast Incremental Updates and Index Replication
		Caching
		Replication
		Web administration interface etc 

2. Extract the zip file and go to the extracted directory and then bin directory and run the following command:
			solr start

3. Apache SOLR runs on port 8983. If you are able to open the following URL : http://localhost:8983/solr then the Apache SOLR is running fine on your system.

4. Create CORE in the Core Admin section. In our case we are using Order core in our integration with Spring Boot. This means we will be indexing Order documents.

5. Then refer the pom.xml, SolrConfig.java, OrderController.java, Order.java, SolrOrderRepository.java files in the repository. Basically we are creating index of Order documents and then searching for the Orders from the index.

6. Sample POST request which will create the index for Order is : 
		URL : http://localhost:8080/order
		Body : 
		{
			"orderid" : 1,
			"orderName" : "Order Name 1",
			"orderDescription" : "Order Description 1",
			"productName" : "Product Name 1",
			"customerName" : "Customer Name 1",
			"customerMobile": "Customer Mobile 1"
		}
		
7. You can fetch that order from the index using GET request:
		URL : http://localhost:8080/order/1
		
8. There are other methods also for fetching the data from the index using other parameters, for that you can refer SolrOrderRepository.java		
		

		
