# MUNI-project
Data analytics + ML approaches for evaluation the % of poor restaurant inspections for grades ‘B’ and ‘C’ in a neighborhood (zip code).

## Task description:
Evaluate the % of poor restaurant inspections for grades ‘B’ and ‘C’ in a neighborhood (zip code).
Get the health complaints specific to Gastrointestinal disease cases from 311 data and aggregate at zip code level.

MUNI project is based on two datasets (311 service requests from 2010 to present, DOHMH New York restaurant inspection results) which were obtained
from the following sources respectively:
https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2010-to-Present/erm2-nwe9
https://data.cityofnewyork.us/Health/DOHMH-New-York-City-Restaurant-Inspection-Results/43nn-pn8j

## Additional information
This project only contains Python code because the amount of data used is well beyond GitHub's size limit.

# Prerequisites for using the code
0. Download required packages from requirements.txt
1. Download the data:

(311): https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2010-to-Present/erm2-nwe9/explore/query/SELECT%0A%20%20%60unique_key%60%2C%0A%20%20%60created_date%60%2C%0A%20%20%60closed_date%60%2C%0A%20%20%60agency%60%2C%0A%20%20%60agency_name%60%2C%0A%20%20%60complaint_type%60%2C%0A%20%20%60descriptor%60%2C%0A%20%20%60location_type%60%2C%0A%20%20%60incident_zip%60%2C%0A%20%20%60incident_address%60%2C%0A%20%20%60street_name%60%2C%0A%20%20%60cross_street_1%60%2C%0A%20%20%60cross_street_2%60%2C%0A%20%20%60intersection_street_1%60%2C%0A%20%20%60intersection_street_2%60%2C%0A%20%20%60address_type%60%2C%0A%20%20%60city%60%2C%0A%20%20%60landmark%60%2C%0A%20%20%60facility_type%60%2C%0A%20%20%60status%60%2C%0A%20%20%60due_date%60%2C%0A%20%20%60resolution_description%60%2C%0A%20%20%60resolution_action_updated_date%60%2C%0A%20%20%60community_board%60%2C%0A%20%20%60bbl%60%2C%0A%20%20%60borough%60%2C%0A%20%20%60x_coordinate_state_plane%60%2C%0A%20%20%60y_coordinate_state_plane%60%2C%0A%20%20%60open_data_channel_type%60%2C%0A%20%20%60park_facility_name%60%2C%0A%20%20%60park_borough%60%2C%0A%20%20%60vehicle_type%60%2C%0A%20%20%60taxi_company_borough%60%2C%0A%20%20%60taxi_pick_up_location%60%2C%0A%20%20%60bridge_highway_name%60%2C%0A%20%20%60bridge_highway_direction%60%2C%0A%20%20%60road_ramp%60%2C%0A%20%20%60bridge_highway_segment%60%2C%0A%20%20%60latitude%60%2C%0A%20%20%60longitude%60%2C%0A%20%20%60location%60%2C%0A%20%20%60%3A%40computed_region_efsh_h5xi%60%2C%0A%20%20%60%3A%40computed_region_f5dn_yrer%60%2C%0A%20%20%60%3A%40computed_region_yeji_bk3q%60%2C%0A%20%20%60%3A%40computed_region_92fq_4b7q%60%2C%0A%20%20%60%3A%40computed_region_sbqj_enih%60%0AWHERE%20caseless_one_of%28%60complaint_type%60%2C%20%22Food%20Poisoning%22%29%0AORDER%20BY%20%60created_date%60%20DESC%20NULL%20FIRST/page/filter

(Restaurants): https://data.cityofnewyork.us/Health/DOHMH-New-York-City-Restaurant-Inspection-Results/43nn-pn8j/explore/query/SELECT%0A%20%20%60camis%60%2C%0A%20%20%60dba%60%2C%0A%20%20%60boro%60%2C%0A%20%20%60building%60%2C%0A%20%20%60street%60%2C%0A%20%20%60zipcode%60%2C%0A%20%20%60phone%60%2C%0A%20%20%60cuisine_description%60%2C%0A%20%20%60inspection_date%60%2C%0A%20%20%60action%60%2C%0A%20%20%60violation_code%60%2C%0A%20%20%60violation_description%60%2C%0A%20%20%60critical_flag%60%2C%0A%20%20%60score%60%2C%0A%20%20%60grade%60%2C%0A%20%20%60grade_date%60%2C%0A%20%20%60record_date%60%2C%0A%20%20%60inspection_type%60%2C%0A%20%20%60latitude%60%2C%0A%20%20%60longitude%60%2C%0A%20%20%60community_board%60%2C%0A%20%20%60council_district%60%2C%0A%20%20%60census_tract%60%2C%0A%20%20%60bin%60%2C%0A%20%20%60bbl%60%2C%0A%20%20%60nta%60%2C%0A%20%20%60location_point1%60%2C%0A%20%20%60%3A%40computed_region_efsh_h5xi%60%2C%0A%20%20%60%3A%40computed_region_f5dn_yrer%60%2C%0A%20%20%60%3A%40computed_region_yeji_bk3q%60%2C%0A%20%20%60%3A%40computed_region_92fq_4b7q%60%2C%0A%20%20%60%3A%40computed_region_sbqj_enih%60%0AWHERE%20caseless_one_of%28%60grade%60%2C%20%22B%22%2C%20%22C%22%29/page/filter
