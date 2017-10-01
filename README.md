# DonorsChoose_Visualization
* Source Code for my blog post: [Interactive Data Visualization with D3.js, DC.js, Python, and MongoDB](http://adilmoujahid.com/posts/2015/01/interactive-data-visualization-d3-dc-python-mongodb/)

#Visit my Blog : http://adilmoujahid.com

## Getting started

The dependencies for the project can be installed using

    $ pip install -r requirements.txt

You can use ``Vagrant`` to start a machine with a MongoDB instance running

    $ vagrant up

Per October 2016 the Donorchoose Opendata can be downloaded from [here](https://research.donorschoose.org/t/download-opendata/33)

Download, extract and rename the dataset (approx. 204 MB compressed and 650 MB when extracted).

    $ wget http://s3.amazonaws.com/open_data/opendata_projects000.gz && zcat opendata_projects000.gz > opendata_projects000.csv
 
To initialize the database you need to imports the csv formatted data into MongoDB collection. 

    $ mongoimport --db donorschoose --collection projects --type csv --headerline --file /vagrant/opendata_projects000.csv 
