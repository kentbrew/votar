# Compare Voting Results with Equipment Type, 2016 US Presidential Election


Get result data:

   curl 'http://data.cnn.com/ELECTION/2016/WI/county/P_county.json' -o ./results/WI_results.txt
   
Add a callback parameter:

   tr -d "\n\r" < ./results/WI_results.txt | sed s/^/"equip['WI']="/ > ./results/WI_results.js

Get equipment data (listed by state fips code):

  curl 'https://www.verifiedvoting.org/wp-content/themes/verified_voting/verifier/api/api.php?db_year=2016&state_fips=55' -o ./equip/WI_equip.txt

Add a callback parameter:

   tr -d "\n\r" < ./equip/WI_equip.txt | sed s/^/"equip['WI']="/ > ./equip/WI_equip.js
   
Do this for all 50 states and you should be able to run index.html.
