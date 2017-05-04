# DonorsChoose_Visualization
* Source Code for my blog post: [Interactive Data Visualization with D3.js, DC.js, Python, and MongoDB](http://adilmoujahid.com/posts/2015/01/interactive-data-visualization-d3-dc-python-mongodb/)

#Visit my Blog : http://adilmoujahid.com

## Getting started

The dependencies for the project can be installed using

    $ pip install -r requirements.txt

You can use ``Vagrant`` to start a machine with a MongoDB instance running

    $ vagrant up

To initialize the database you need to download the data

    $ wget http://s3.amazonaws.com/open_data/opendata_projects000.gz

and import it

    $ mongoimport -d donorschoose -c projects --type csv --file /vagrant/opendata_projects.csv --fields "_id,_projectid,_teacher_acctid,_schoolid,school_ncesid,school_latitude,school_longitude,school_city,school_state,school_zip,school_metro,school_district,school_county,school_charter,school_magnet,school_year_round,school_nlns,school_kipp,school_charter_ready_promise,teacher_prefix,teacher_teach_for_america,teacher_ny_teaching_fellow,primary_focus_subject,primary_focus_area,secondary_focus_subject,secondary_focus_area,resource_type,poverty_level,grade_level,vendor_shipping_charges,sales_tax,payment_processing_charges,fulfillment_labor_materials,total_price_excluding_optional_support,total_price_including_optional_support,students_reached,total_donations,num_donors,eligible_double_your_impact_match,eligible_almost_home_match,funding_status,date_posted,date_completed,date_thank_you_packet_mailed,date_expiration"
