

root@localhost:OPENX_V1_STATS 17:51:31>DESCRIBE OPENX_V1_STATS.ox_data_summary_rtb_daily;
+---------------------------+----------------------------+------+-----+---------+----------------+
| Field                     | Type                       | Null | Key | Default | Extra          |
+---------------------------+----------------------------+------+-----+---------+----------------+
| data_summary_rtb_daily_id | bigint(20) unsigned        | NO   | PRI | NULL    | auto_increment |
| date_time                 | datetime /* mariadb-5.3 */ | NO   | PRI | NULL    |                |
| ad_id                     | int(10) unsigned           | NO   |     | NULL    |                |
| zone_id                   | int(10) unsigned           | NO   |     | NULL    |                |
| campaignid                | mediumint(8) unsigned      | NO   |     | NULL    |                |
| c_type                    | smallint(5) unsigned       | NO   |     | NULL    |                |
| d_type                    | varchar(16)                | YES  |     | NULL    |                |
| clientid                  | mediumint(8) unsigned      | YES  |     | NULL    |                |
| affiliateid               | mediumint(8) unsigned      | YES  |     | NULL    |                |
| bids                      | int(10) unsigned           | NO   |     | 0       |                |
| requests                  | int(10) unsigned           | NO   |     | 0       |                |
| updated                   | datetime /* mariadb-5.3 */ | YES  |     | NULL    |                |
+---------------------------+----------------------------+------+-----+---------+----------------+
12 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:51:34>DESCRIBE OPENX_V1_STATS.ox_data_summary_ad_hourly_zone;
 OPENX_V1_STATS.ox_data_summary_astg_tagging_type_stats_hourly;
DESCRIBE OPENX_V1_STATS.ox_log_maintenance_priority;
DESCRIBE OPENX_V1_STATS.ox_data_all_creatives_log;
DESCRIBE OPENX_V1_STATS.ox_data_intermediate_ad;
DESCRIBE OPENX_V1_STATS.ox_log_maintenance_statistics;
DESCRIBE OPENX_V1_STATS.ox_data_summary_ad_daily_ad;
DESCRIBE OPENX_V1_STATS.ox_data_summary_rtb_daily_campaign;
DESCRIBE OPENX_V1_STATS.ox_data_summary_rtb_hourly_ad;
DESCRIBE OPENX_V1_STATS.ox_data_summary_rtb_hourly;
DESCRIBE OPENX_V1_STATS.ox_data_summary_ad_hourly_campaign;
DESCRIBE OPENX_V1_STATS.ox_data_intermediate_ad_zone;
DESCRIBE OPENX_V1_STATS.ox_data_summary_ad_hourly_zone_ctype;
DESCRIBE OPENX_V1_STATS.ox_wp_data_raw_a_item;
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| Field                                       | Type                       | Null | Key | Default    | Extra          |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| data_summary_ad_hourly_zone_id              | bigint(20) unsigned        | NO   | PRI | NULL       | auto_increment |
| date_time                                   | datetime /* mariadb-5.3 */ | NO   | PRI | NULL       |                |
| zone_id                                     | int(10) unsigned           | NO   | MUL | NULL       |                |
| bids                                        | int(10) unsigned           | YES  |     | 0          |                |
| wins                                        | int(10) unsigned           | YES  |     | 0          |                |
| requests                                    | int(10) unsigned           | NO   |     | 0          |                |
| impressions                                 | int(10) unsigned           | NO   |     | 0          |                |
| clicks                                      | int(10) unsigned           | NO   |     | 0          |                |
| conversions                                 | int(10) unsigned           | NO   |     | 0          |                |
| total_basket_value                          | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_num_items                             | int(11)                    | YES  |     | NULL       |                |
| total_revenue                               | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_cost                                  | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_techcost                              | decimal(10,4)              | YES  |     | NULL       |                |
| updated                                     | datetime /* mariadb-5.3 */ | NO   |     | NULL       |                |
| assisted_conversions                        | int(10)                    | NO   |     | 0          |                |
| total_assisted_basket_value                 | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_assisted_num_items                    | int(10)                    | NO   |     | 0          |                |
| view_through_conversions                    | int(10)                    | NO   |     | 0          |                |
| total_view_through_basket_value             | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_view_through_num_items                | int(10)                    | NO   |     | 0          |                |
| total_rscpm                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| oneday_conversions                          | int(10)                    | NO   |     | 0          |                |
| total_oneday_basket_value                   | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_oneday_num_items                      | int(10)                    | YES  |     | 0          |                |
| total_gross                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| abuse_click                                 | int(10) unsigned           | NO   |     | 0          |                |
| over_click                                  | int(10) unsigned           | NO   |     | 0          |                |
| currency_id                                 | mediumint(9) unsigned      | NO   |     | 1          |                |
| new_user_click                              | int(10) unsigned           | YES  |     | 0          |                |
| campaignid                                  | mediumint(9) unsigned      | YES  |     | NULL       |                |
| d_type                                      | varchar(16)                | YES  |     | NULL       |                |
| c_type                                      | smallint(6) unsigned       | YES  |     | NULL       |                |
| clientid                                    | mediumint(9) unsigned      | YES  |     | NULL       |                |
| affiliateid                                 | mediumint(9) unsigned      | YES  |     | NULL       |                |
| dmp_code                                    | int(10) unsigned           | YES  |     | NULL       |                |
| dmp_sales_code                              | int(10) unsigned           | YES  |     | NULL       |                |
| total_dmp                                   | decimal(23,8)              | YES  |     | NULL       |                |
| play_impressions                            | int(10) unsigned           | YES  |     | NULL       |                |
| avg_play_time                               | bigint(20) unsigned        | YES  |     | NULL       |                |
| default_conversions                         | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_conversions_basket_value      | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_conversions_num_items         | int(10) unsigned           | YES  |     | NULL       |                |
| cross_conversions                           | int(10) unsigned           | YES  |     | NULL       |                |
| total_cross_conversions_basket_value        | decimal(23,8)              | YES  |     | NULL       |                |
| total_cross_conversions_num_items           | int(10) unsigned           | YES  |     | NULL       |                |
| plays                                       | int(10) unsigned           | NO   |     | 0          |                |
| abuse_play                                  | int(10) unsigned           | NO   |     | 0          |                |
| over_play                                   | int(10) unsigned           | NO   |     | 0          |                |
| new_user_play                               | int(10) unsigned           | NO   |     | 0          |                |
| play_conversions                            | int(10) unsigned           | NO   |     | 0          |                |
| total_play_conversions_basket_value         | decimal(23,8)              | YES  |     | NULL       |                |
| total_play_conversions_num_items            | int(10) unsigned           | YES  |     | NULL       |                |
| oneday_play_conversions                     | int(10) unsigned           | YES  |     | NULL       |                |
| total_oneday_play_conversions_basket_value  | decimal(23,8)              | YES  |     | NULL       |                |
| total_oneday_play_conversions_num_items     | int(10) unsigned           | YES  |     | NULL       |                |
| default_play_conversions                    | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_play_conversions_basket_value | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_play_conversions_num_items    | int(10) unsigned           | YES  |     | NULL       |                |
...skipping...
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| Field                                       | Type                       | Null | Key | Default    | Extra          |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| data_summary_ad_hourly_zone_id              | bigint(20) unsigned        | NO   | PRI | NULL       | auto_increment |
| date_time                                   | datetime /* mariadb-5.3 */ | NO   | PRI | NULL       |                |
| zone_id                                     | int(10) unsigned           | NO   | MUL | NULL       |                |
| bids                                        | int(10) unsigned           | YES  |     | 0          |                |
| wins                                        | int(10) unsigned           | YES  |     | 0          |                |
| requests                                    | int(10) unsigned           | NO   |     | 0          |                |
| impressions                                 | int(10) unsigned           | NO   |     | 0          |                |
| clicks                                      | int(10) unsigned           | NO   |     | 0          |                |
| conversions                                 | int(10) unsigned           | NO   |     | 0          |                |
| total_basket_value                          | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_num_items                             | int(11)                    | YES  |     | NULL       |                |
| total_revenue                               | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_cost                                  | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_techcost                              | decimal(10,4)              | YES  |     | NULL       |                |
| updated                                     | datetime /* mariadb-5.3 */ | NO   |     | NULL       |                |
| assisted_conversions                        | int(10)                    | NO   |     | 0          |                |
| total_assisted_basket_value                 | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_assisted_num_items                    | int(10)                    | NO   |     | 0          |                |
| view_through_conversions                    | int(10)                    | NO   |     | 0          |                |
| total_view_through_basket_value             | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_view_through_num_items                | int(10)                    | NO   |     | 0          |                |
| total_rscpm                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| oneday_conversions                          | int(10)                    | NO   |     | 0          |                |
| total_oneday_basket_value                   | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_oneday_num_items                      | int(10)                    | YES  |     | 0          |                |
| total_gross                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| abuse_click                                 | int(10) unsigned           | NO   |     | 0          |                |
| over_click                                  | int(10) unsigned           | NO   |     | 0          |                |
| currency_id                                 | mediumint(9) unsigned      | NO   |     | 1          |                |
| new_user_click                              | int(10) unsigned           | YES  |     | 0          |                |
| campaignid                                  | mediumint(9) unsigned      | YES  |     | NULL       |                |
| d_type                                      | varchar(16)                | YES  |     | NULL       |                |
| c_type                                      | smallint(6) unsigned       | YES  |     | NULL       |                |
| clientid                                    | mediumint(9) unsigned      | YES  |     | NULL       |                |
| affiliateid                                 | mediumint(9) unsigned      | YES  |     | NULL       |                |
| dmp_code                                    | int(10) unsigned           | YES  |     | NULL       |                |
| dmp_sales_code                              | int(10) unsigned           | YES  |     | NULL       |                |
| total_dmp                                   | decimal(23,8)              | YES  |     | NULL       |                |
| play_impressions                            | int(10) unsigned           | YES  |     | NULL       |                |
| avg_play_time                               | bigint(20) unsigned        | YES  |     | NULL       |                |
| default_conversions                         | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_conversions_basket_value      | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_conversions_num_items         | int(10) unsigned           | YES  |     | NULL       |                |
| cross_conversions                           | int(10) unsigned           | YES  |     | NULL       |                |
| total_cross_conversions_basket_value        | decimal(23,8)              | YES  |     | NULL       |                |
| total_cross_conversions_num_items           | int(10) unsigned           | YES  |     | NULL       |                |
| plays                                       | int(10) unsigned           | NO   |     | 0          |                |
| abuse_play                                  | int(10) unsigned           | NO   |     | 0          |                |
| over_play                                   | int(10) unsigned           | NO   |     | 0          |                |
| new_user_play                               | int(10) unsigned           | NO   |     | 0          |                |
| play_conversions                            | int(10) unsigned           | NO   |     | 0          |                |
| total_play_conversions_basket_value         | decimal(23,8)              | YES  |     | NULL       |                |
| total_play_conversions_num_items            | int(10) unsigned           | YES  |     | NULL       |                |
| oneday_play_conversions                     | int(10) unsigned           | YES  |     | NULL       |                |
| total_oneday_play_conversions_basket_value  | decimal(23,8)              | YES  |     | NULL       |                |
| total_oneday_play_conversions_num_items     | int(10) unsigned           | YES  |     | NULL       |                |
| default_play_conversions                    | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_play_conversions_basket_value | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_play_conversions_num_items    | int(10) unsigned           | YES  |     | NULL       |                |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
59 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:51:41>DESCRIBE OPENX_V1_STATS.ox_data_summary_rtb_daily;
+---------------------------+----------------------------+------+-----+---------+----------------+
| Field                     | Type                       | Null | Key | Default | Extra          |
+---------------------------+----------------------------+------+-----+---------+----------------+
| data_summary_rtb_daily_id | bigint(20) unsigned        | NO   | PRI | NULL    | auto_increment |
| date_time                 | datetime /* mariadb-5.3 */ | NO   | PRI | NULL    |                |
| ad_id                     | int(10) unsigned           | NO   |     | NULL    |                |
| zone_id                   | int(10) unsigned           | NO   |     | NULL    |                |
| campaignid                | mediumint(8) unsigned      | NO   |     | NULL    |                |
| c_type                    | smallint(5) unsigned       | NO   |     | NULL    |                |
| d_type                    | varchar(16)                | YES  |     | NULL    |                |
| clientid                  | mediumint(8) unsigned      | YES  |     | NULL    |                |
| affiliateid               | mediumint(8) unsigned      | YES  |     | NULL    |                |
| bids                      | int(10) unsigned           | NO   |     | 0       |                |
| requests                  | int(10) unsigned           | NO   |     | 0       |                |
| updated                   | datetime /* mariadb-5.3 */ | YES  |     | NULL    |                |
+---------------------------+----------------------------+------+-----+---------+----------------+
12 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:52:13>DESCRIBE OPENX_V1_STATS.ox_data_summary_ad_hourly_zone;
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| Field                                       | Type                       | Null | Key | Default    | Extra          |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| data_summary_ad_hourly_zone_id              | bigint(20) unsigned        | NO   | PRI | NULL       | auto_increment |
| date_time                                   | datetime /* mariadb-5.3 */ | NO   | PRI | NULL       |                |
| zone_id                                     | int(10) unsigned           | NO   | MUL | NULL       |                |
| bids                                        | int(10) unsigned           | YES  |     | 0          |                |
| wins                                        | int(10) unsigned           | YES  |     | 0          |                |
| requests                                    | int(10) unsigned           | NO   |     | 0          |                |
| impressions                                 | int(10) unsigned           | NO   |     | 0          |                |
| clicks                                      | int(10) unsigned           | NO   |     | 0          |                |
| conversions                                 | int(10) unsigned           | NO   |     | 0          |                |
| total_basket_value                          | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_num_items                             | int(11)                    | YES  |     | NULL       |                |
| total_revenue                               | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_cost                                  | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_techcost                              | decimal(10,4)              | YES  |     | NULL       |                |
| updated                                     | datetime /* mariadb-5.3 */ | NO   |     | NULL       |                |
| assisted_conversions                        | int(10)                    | NO   |     | 0          |                |
| total_assisted_basket_value                 | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_assisted_num_items                    | int(10)                    | NO   |     | 0          |                |
| view_through_conversions                    | int(10)                    | NO   |     | 0          |                |
| total_view_through_basket_value             | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_view_through_num_items                | int(10)                    | NO   |     | 0          |                |
| total_rscpm                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| oneday_conversions                          | int(10)                    | NO   |     | 0          |                |
| total_oneday_basket_value                   | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_oneday_num_items                      | int(10)                    | YES  |     | 0          |                |
| total_gross                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| abuse_click                                 | int(10) unsigned           | NO   |     | 0          |                |
| over_click                                  | int(10) unsigned           | NO   |     | 0          |                |
| currency_id                                 | mediumint(9) unsigned      | NO   |     | 1          |                |
| new_user_click                              | int(10) unsigned           | YES  |     | 0          |                |
| campaignid                                  | mediumint(9) unsigned      | YES  |     | NULL       |                |
| d_type                                      | varchar(16)                | YES  |     | NULL       |                |
| c_type                                      | smallint(6) unsigned       | YES  |     | NULL       |                |
| clientid                                    | mediumint(9) unsigned      | YES  |     | NULL       |                |
| affiliateid                                 | mediumint(9) unsigned      | YES  |     | NULL       |                |
| dmp_code                                    | int(10) unsigned           | YES  |     | NULL       |                |
| dmp_sales_code                              | int(10) unsigned           | YES  |     | NULL       |                |
| total_dmp                                   | decimal(23,8)              | YES  |     | NULL       |                |
| play_impressions                            | int(10) unsigned           | YES  |     | NULL       |                |
| avg_play_time                               | bigint(20) unsigned        | YES  |     | NULL       |                |
| default_conversions                         | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_conversions_basket_value      | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_conversions_num_items         | int(10) unsigned           | YES  |     | NULL       |                |
| cross_conversions                           | int(10) unsigned           | YES  |     | NULL       |                |
| total_cross_conversions_basket_value        | decimal(23,8)              | YES  |     | NULL       |                |
| total_cross_conversions_num_items           | int(10) unsigned           | YES  |     | NULL       |                |
| plays                                       | int(10) unsigned           | NO   |     | 0          |                |
| abuse_play                                  | int(10) unsigned           | NO   |     | 0          |                |
| over_play                                   | int(10) unsigned           | NO   |     | 0          |                |
| new_user_play                               | int(10) unsigned           | NO   |     | 0          |                |
| play_conversions                            | int(10) unsigned           | NO   |     | 0          |                |
| total_play_conversions_basket_value         | decimal(23,8)              | YES  |     | NULL       |                |
| total_play_conversions_num_items            | int(10) unsigned           | YES  |     | NULL       |                |
| oneday_play_conversions                     | int(10) unsigned           | YES  |     | NULL       |                |
| total_oneday_play_conversions_basket_value  | decimal(23,8)              | YES  |     | NULL       |                |
| total_oneday_play_conversions_num_items     | int(10) unsigned           | YES  |     | NULL       |                |
| default_play_conversions                    | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_play_conversions_basket_value | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_play_conversions_num_items    | int(10) unsigned           | YES  |     | NULL       |                |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
59 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:52:19>DESCRIBE OPENX_V1_STATS.ox_data_summary_ad_hourly;
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| Field                                       | Type                       | Null | Key | Default    | Extra          |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| data_summary_ad_hourly_id                   | bigint(20) unsigned        | NO   | PRI | NULL       | auto_increment |
| date_time                                   | datetime /* mariadb-5.3 */ | NO   | PRI | NULL       |                |
| ad_id                                       | int(10) unsigned           | NO   | MUL | NULL       |                |
| creative_id                                 | int(10) unsigned           | NO   |     | NULL       |                |
| zone_id                                     | int(10) unsigned           | NO   | MUL | NULL       |                |
| bids                                        | int(10) unsigned           | YES  |     | 0          |                |
| wins                                        | int(10) unsigned           | YES  |     | 0          |                |
| requests                                    | int(10) unsigned           | NO   |     | 0          |                |
| impressions                                 | int(10) unsigned           | NO   |     | 0          |                |
| clicks                                      | int(10) unsigned           | NO   |     | 0          |                |
| conversions                                 | int(10) unsigned           | NO   |     | 0          |                |
| total_basket_value                          | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_num_items                             | int(11)                    | YES  |     | NULL       |                |
| total_revenue                               | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_cost                                  | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_techcost                              | decimal(10,4)              | YES  |     | NULL       |                |
| updated                                     | datetime /* mariadb-5.3 */ | NO   |     | NULL       |                |
| assisted_conversions                        | int(10)                    | NO   |     | 0          |                |
| total_assisted_basket_value                 | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_assisted_num_items                    | int(10)                    | NO   |     | 0          |                |
| view_through_conversions                    | int(10)                    | NO   |     | 0          |                |
| total_view_through_basket_value             | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_view_through_num_items                | int(10)                    | NO   |     | 0          |                |
| total_rscpm                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| oneday_conversions                          | int(10)                    | NO   |     | 0          |                |
| total_oneday_basket_value                   | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_oneday_num_items                      | int(10)                    | YES  |     | 0          |                |
| total_gross                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| abuse_click                                 | int(10) unsigned           | NO   |     | 0          |                |
| over_click                                  | int(10) unsigned           | NO   |     | 0          |                |
| currency_id                                 | mediumint(9) unsigned      | NO   |     | 1          |                |
| new_user_click                              | int(10) unsigned           | YES  |     | 0          |                |
| campaignid                                  | mediumint(9) unsigned      | YES  |     | NULL       |                |
| d_type                                      | varchar(16)                | YES  |     | NULL       |                |
| c_type                                      | smallint(6) unsigned       | YES  |     | NULL       |                |
| clientid                                    | mediumint(9) unsigned      | YES  |     | NULL       |                |
| affiliateid                                 | mediumint(9) unsigned      | YES  |     | NULL       |                |
| dmp_code                                    | int(10) unsigned           | YES  |     | NULL       |                |
| dmp_sales_code                              | int(10) unsigned           | YES  |     | NULL       |                |
| total_dmp                                   | decimal(23,8)              | YES  |     | NULL       |                |
| play_impressions                            | int(10) unsigned           | YES  |     | NULL       |                |
| avg_play_time                               | bigint(20) unsigned        | YES  |     | NULL       |                |
| default_conversions                         | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_conversions_basket_value      | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_conversions_num_items         | int(10) unsigned           | YES  |     | NULL       |                |
| cross_conversions                           | int(10) unsigned           | YES  |     | NULL       |                |
| total_cross_conversions_basket_value        | decimal(23,8)              | YES  |     | NULL       |                |
| total_cross_conversions_num_items           | int(10) unsigned           | YES  |     | NULL       |                |
| plays                                       | int(10) unsigned           | NO   |     | 0          |                |
| abuse_play                                  | int(10) unsigned           | NO   |     | 0          |                |
| over_play                                   | int(10) unsigned           | NO   |     | 0          |                |
| new_user_play                               | int(10) unsigned           | NO   |     | 0          |                |
| play_conversions                            | int(10) unsigned           | NO   |     | 0          |                |
| total_play_conversions_basket_value         | decimal(23,8)              | YES  |     | NULL       |                |
| total_play_conversions_num_items            | int(10) unsigned           | YES  |     | NULL       |                |
| oneday_play_conversions                     | int(10) unsigned           | YES  |     | NULL       |                |
| total_oneday_play_conversions_basket_value  | decimal(23,8)              | YES  |     | NULL       |                |
| total_oneday_play_conversions_num_items     | int(10) unsigned           | YES  |     | NULL       |                |
| default_play_conversions                    | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_play_conversions_basket_value | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_play_conversions_num_items    | int(10) unsigned           | YES  |     | NULL       |                |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
61 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:52:35>DESCRIBE OPENX_V1_STATS.ox_data_summary_rtb_daily_zone;
+--------------------------------+----------------------------+------+-----+---------+----------------+
| Field                          | Type                       | Null | Key | Default | Extra          |
+--------------------------------+----------------------------+------+-----+---------+----------------+
| data_summary_rtb_daily_zone_id | bigint(20) unsigned        | NO   | PRI | NULL    | auto_increment |
| date_time                      | datetime /* mariadb-5.3 */ | NO   | PRI | NULL    |                |
| zone_id                        | int(10) unsigned           | NO   | MUL | NULL    |                |
| affiliateid                    | mediumint(8) unsigned      | YES  |     | NULL    |                |
| bids                           | int(10) unsigned           | NO   |     | 0       |                |
| requests                       | int(10) unsigned           | NO   |     | 0       |                |
| updated                        | datetime /* mariadb-5.3 */ | YES  |     | NULL    |                |
+--------------------------------+----------------------------+------+-----+---------+----------------+
7 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:52:43>DESCRIBE OPENX_V1_STATS.ox_data_intermediate_ad_campaign;
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| Field                                       | Type                       | Null | Key | Default    | Extra          |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| data_intermediate_ad_campaign_id            | bigint(20) unsigned        | NO   | PRI | NULL       | auto_increment |
| date_time                                   | datetime /* mariadb-5.3 */ | NO   | PRI | NULL       |                |
| campaignid                                  | mediumint(9) unsigned      | NO   | MUL | NULL       |                |
| bids                                        | int(10) unsigned           | YES  |     | 0          |                |
| wins                                        | int(10) unsigned           | YES  |     | 0          |                |
| requests                                    | int(10) unsigned           | NO   |     | 0          |                |
| impressions                                 | int(10) unsigned           | NO   |     | 0          |                |
| clicks                                      | int(10) unsigned           | NO   |     | 0          |                |
| conversions                                 | int(10) unsigned           | NO   |     | 0          |                |
| total_basket_value                          | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_num_items                             | int(11)                    | YES  |     | NULL       |                |
| total_revenue                               | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_cost                                  | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_techcost                              | decimal(10,4)              | YES  |     | NULL       |                |
| updated                                     | datetime /* mariadb-5.3 */ | NO   |     | NULL       |                |
| assisted_conversions                        | int(10)                    | NO   |     | 0          |                |
| total_assisted_basket_value                 | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_assisted_num_items                    | int(10)                    | NO   |     | 0          |                |
| view_through_conversions                    | int(10)                    | NO   |     | 0          |                |
| total_view_through_basket_value             | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_view_through_num_items                | int(10)                    | NO   |     | 0          |                |
| total_rscpm                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| oneday_conversions                          | int(10)                    | NO   |     | 0          |                |
| total_oneday_basket_value                   | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_oneday_num_items                      | int(10)                    | YES  |     | 0          |                |
| total_gross                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| abuse_click                                 | int(10) unsigned           | NO   |     | 0          |                |
| over_click                                  | int(10) unsigned           | NO   |     | 0          |                |
| currency_id                                 | mediumint(9) unsigned      | NO   |     | 1          |                |
| new_user_click                              | int(10) unsigned           | YES  |     | 0          |                |
| d_type                                      | varchar(16)                | YES  |     | NULL       |                |
| c_type                                      | smallint(6) unsigned       | YES  |     | NULL       |                |
| clientid                                    | mediumint(9) unsigned      | YES  | MUL | NULL       |                |
| affiliateid                                 | mediumint(9) unsigned      | YES  |     | NULL       |                |
| dmp_code                                    | int(10) unsigned           | YES  |     | NULL       |                |
| dmp_sales_code                              | int(10) unsigned           | YES  |     | NULL       |                |
| total_dmp                                   | decimal(23,8)              | YES  |     | NULL       |                |
| play_impressions                            | int(10) unsigned           | YES  |     | NULL       |                |
| avg_play_time                               | bigint(20) unsigned        | YES  |     | NULL       |                |
| default_conversions                         | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_conversions_basket_value      | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_conversions_num_items         | int(10) unsigned           | YES  |     | NULL       |                |
| cross_conversions                           | int(10) unsigned           | YES  |     | NULL       |                |
| total_cross_conversions_basket_value        | decimal(23,8)              | YES  |     | NULL       |                |
| total_cross_conversions_num_items           | int(10) unsigned           | YES  |     | NULL       |                |
| plays                                       | int(10) unsigned           | NO   |     | 0          |                |
| abuse_play                                  | int(10) unsigned           | NO   |     | 0          |                |
| over_play                                   | int(10) unsigned           | NO   |     | 0          |                |
| new_user_play                               | int(10) unsigned           | NO   |     | 0          |                |
| play_conversions                            | int(10) unsigned           | NO   |     | 0          |                |
| total_play_conversions_basket_value         | decimal(23,8)              | YES  |     | NULL       |                |
| total_play_conversions_num_items            | int(10) unsigned           | YES  |     | NULL       |                |
| oneday_play_conversions                     | int(10) unsigned           | YES  |     | NULL       |                |
| total_oneday_play_conversions_basket_value  | decimal(23,8)              | YES  |     | NULL       |                |
| total_oneday_play_conversions_num_items     | int(10) unsigned           | YES  |     | NULL       |                |
| default_play_conversions                    | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_play_conversions_basket_value | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_play_conversions_num_items    | int(10) unsigned           | YES  |     | NULL       |                |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
58 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:52:47>DESCRIBE OPENX_V1_STATS.ox_data_summary_rtb_hourly_zone;
+---------------------------------+----------------------------+------+-----+---------+----------------+
| Field                           | Type                       | Null | Key | Default | Extra          |
+---------------------------------+----------------------------+------+-----+---------+----------------+
| data_summary_rtb_hourly_zone_id | bigint(20) unsigned        | NO   | PRI | NULL    | auto_increment |
| date_time                       | datetime /* mariadb-5.3 */ | NO   | PRI | NULL    |                |
| zone_id                         | int(10) unsigned           | NO   | MUL | NULL    |                |
| affiliateid                     | mediumint(8) unsigned      | YES  |     | NULL    |                |
| bids                            | int(10) unsigned           | NO   |     | 0       |                |
| requests                        | int(10) unsigned           | NO   |     | 0       |                |
| updated                         | datetime /* mariadb-5.3 */ | YES  |     | NULL    |                |
+---------------------------------+----------------------------+------+-----+---------+----------------+
7 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:52:56>DESCRIBE OPENX_V1_STATS.ox_data_summary_ad_daily_campaign;
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| Field                                       | Type                       | Null | Key | Default    | Extra          |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| data_summary_ad_daily_campaign_id           | bigint(20) unsigned        | NO   | PRI | NULL       | auto_increment |
| date_time                                   | datetime /* mariadb-5.3 */ | NO   | PRI | NULL       |                |
| campaignid                                  | mediumint(9) unsigned      | NO   | MUL | NULL       |                |
| bids                                        | int(10) unsigned           | YES  |     | 0          |                |
| wins                                        | int(10) unsigned           | YES  |     | 0          |                |
| requests                                    | int(10) unsigned           | NO   |     | 0          |                |
| impressions                                 | int(10) unsigned           | NO   |     | 0          |                |
| clicks                                      | int(10) unsigned           | NO   |     | 0          |                |
| conversions                                 | int(10) unsigned           | NO   |     | 0          |                |
| total_basket_value                          | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_num_items                             | int(11)                    | YES  |     | NULL       |                |
| total_revenue                               | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_cost                                  | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_techcost                              | decimal(10,4)              | YES  |     | NULL       |                |
| updated                                     | datetime /* mariadb-5.3 */ | NO   |     | NULL       |                |
| assisted_conversions                        | int(10)                    | NO   |     | 0          |                |
| total_assisted_basket_value                 | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_assisted_num_items                    | int(10)                    | NO   |     | 0          |                |
| view_through_conversions                    | int(10)                    | NO   |     | 0          |                |
| total_view_through_basket_value             | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_view_through_num_items                | int(10) unsigned           | YES  |     | NULL       |                |
| total_rscpm                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| oneday_conversions                          | int(10)                    | NO   |     | 0          |                |
| total_oneday_basket_value                   | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_oneday_num_items                      | int(10)                    | YES  |     | 0          |                |
| total_gross                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| abuse_click                                 | int(10) unsigned           | NO   |     | 0          |                |
| over_click                                  | int(10) unsigned           | NO   |     | 0          |                |
| currency_id                                 | mediumint(9) unsigned      | NO   |     | 1          |                |
| new_user_click                              | int(10) unsigned           | YES  |     | 0          |                |
| d_type                                      | varchar(16)                | YES  |     | NULL       |                |
| c_type                                      | smallint(6) unsigned       | YES  |     | NULL       |                |
| clientid                                    | mediumint(9) unsigned      | YES  |     | NULL       |                |
| affiliateid                                 | mediumint(9) unsigned      | YES  |     | NULL       |                |
| dmp_code                                    | int(10) unsigned           | YES  |     | NULL       |                |
| dmp_sales_code                              | int(10) unsigned           | YES  |     | NULL       |                |
| total_dmp                                   | decimal(23,8)              | YES  |     | NULL       |                |
| play_impressions                            | int(10) unsigned           | YES  |     | NULL       |                |
| avg_play_time                               | bigint(20) unsigned        | YES  |     | NULL       |                |
| default_conversions                         | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_conversions_basket_value      | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_conversions_num_items         | int(10) unsigned           | YES  |     | NULL       |                |
| cross_conversions                           | int(10) unsigned           | YES  |     | NULL       |                |
| total_cross_conversions_basket_value        | decimal(23,8)              | YES  |     | NULL       |                |
| total_cross_conversions_num_items           | int(10) unsigned           | YES  |     | NULL       |                |
| plays                                       | int(10) unsigned           | NO   |     | 0          |                |
| abuse_play                                  | int(10) unsigned           | NO   |     | 0          |                |
| over_play                                   | int(10) unsigned           | NO   |     | 0          |                |
| new_user_play                               | int(10) unsigned           | NO   |     | 0          |                |
| play_conversions                            | int(10) unsigned           | NO   |     | 0          |                |
| total_play_conversions_basket_value         | decimal(23,8)              | YES  |     | NULL       |                |
| total_play_conversions_num_items            | int(10) unsigned           | YES  |     | NULL       |                |
| oneday_play_conversions                     | int(10) unsigned           | YES  |     | NULL       |                |
| total_oneday_play_conversions_basket_value  | decimal(23,8)              | YES  |     | NULL       |                |
| total_oneday_play_conversions_num_items     | int(10) unsigned           | YES  |     | NULL       |                |
| default_play_conversions                    | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_play_conversions_basket_value | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_play_conversions_num_items    | int(10) unsigned           | YES  |     | NULL       |                |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
58 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:53:01>DESCRIBE OPENX_V1_STATS.ox_tg_tagged_user;
+-----------------+----------------------------+------+-----+---------+-------+
| Field           | Type                       | Null | Key | Default | Extra |
+-----------------+----------------------------+------+-----+---------+-------+
| clientid        | int(11)                    | NO   | PRI | NULL    |       |
| date_time       | datetime /* mariadb-5.3 */ | NO   | PRI | NULL    |       |
| tagged_total    | int(11)                    | NO   |     | 0       |       |
| tagged_pc       | int(11)                    | NO   |     | 0       |       |
| tagged_pc_agent | int(11) unsigned           | NO   |     | 0       |       |
| tagged_mobile   | int(11)                    | NO   |     | 0       |       |
| andr_web        | int(11) unsigned           | NO   |     | 0       |       |
| ios_web         | int(11) unsigned           | NO   |     | 0       |       |
| andr_app        | int(11) unsigned           | NO   |     | 0       |       |
| ios_app         | int(11) unsigned           | NO   |     | 0       |       |
| visit           | int(11)                    | NO   |     | 0       |       |
| appear          | int(11)                    | NO   |     | 0       |       |
| appeared_pc_uv  | bigint(20)                 | YES  |     | 0       |       |
| appeared_aw_uv  | bigint(20)                 | YES  |     | 0       |       |
| appeared_iw_uv  | bigint(20)                 | YES  |     | 0       |       |
| appeared_aa_uv  | bigint(20)                 | YES  |     | 0       |       |
| appeared_ia_uv  | bigint(20)                 | YES  |     | 0       |       |
| new             | int(11)                    | NO   |     | 0       |       |
| etc             | int(11) unsigned           | NO   |     | 0       |       |
| hcuid_cnt       | int(11)                    | NO   |     | 0       |       |
+-----------------+----------------------------+------+-----+---------+-------+
20 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:53:09>DESCRIBE OPENX_V1_STATS.ox_data_summary_ad_hourly_ad;
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| Field                                       | Type                       | Null | Key | Default    | Extra          |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| data_summary_ad_hourly_ad_id                | bigint(20) unsigned        | NO   | PRI | NULL       | auto_increment |
| date_time                                   | datetime /* mariadb-5.3 */ | NO   | PRI | NULL       |                |
| ad_id                                       | int(10) unsigned           | NO   | MUL | NULL       |                |
| bids                                        | int(10) unsigned           | YES  |     | 0          |                |
| wins                                        | int(10) unsigned           | YES  |     | 0          |                |
| requests                                    | int(10) unsigned           | NO   |     | 0          |                |
| impressions                                 | int(10) unsigned           | NO   |     | 0          |                |
| clicks                                      | int(10) unsigned           | NO   |     | 0          |                |
| conversions                                 | int(10) unsigned           | NO   |     | 0          |                |
| total_basket_value                          | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_num_items                             | int(11)                    | YES  |     | NULL       |                |
| total_revenue                               | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_cost                                  | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_techcost                              | decimal(10,4)              | YES  |     | NULL       |                |
| updated                                     | datetime /* mariadb-5.3 */ | NO   |     | NULL       |                |
| assisted_conversions                        | int(10)                    | NO   |     | 0          |                |
| total_assisted_basket_value                 | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_assisted_num_items                    | int(10)                    | NO   |     | 0          |                |
| view_through_conversions                    | int(10)                    | NO   |     | 0          |                |
| total_view_through_basket_value             | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_view_through_num_items                | int(10)                    | NO   |     | 0          |                |
| total_rscpm                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| oneday_conversions                          | int(10)                    | NO   |     | 0          |                |
| total_oneday_basket_value                   | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_oneday_num_items                      | int(10)                    | YES  |     | 0          |                |
| total_gross                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| abuse_click                                 | int(10) unsigned           | NO   |     | 0          |                |
| over_click                                  | int(10) unsigned           | NO   |     | 0          |                |
| currency_id                                 | mediumint(9) unsigned      | NO   |     | 1          |                |
| new_user_click                              | int(10) unsigned           | YES  |     | 0          |                |
| campaignid                                  | mediumint(9) unsigned      | YES  |     | NULL       |                |
| d_type                                      | varchar(16)                | YES  |     | NULL       |                |
| c_type                                      | smallint(6) unsigned       | YES  |     | NULL       |                |
| clientid                                    | mediumint(9) unsigned      | YES  |     | NULL       |                |
| affiliateid                                 | mediumint(9) unsigned      | YES  |     | NULL       |                |
| dmp_code                                    | int(10) unsigned           | YES  |     | NULL       |                |
| dmp_sales_code                              | int(10) unsigned           | YES  |     | NULL       |                |
| total_dmp                                   | decimal(23,8)              | YES  |     | NULL       |                |
| play_impressions                            | int(10) unsigned           | YES  |     | NULL       |                |
| avg_play_time                               | bigint(20) unsigned        | YES  |     | NULL       |                |
| default_conversions                         | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_conversions_basket_value      | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_conversions_num_items         | int(10) unsigned           | YES  |     | NULL       |                |
| cross_conversions                           | int(10) unsigned           | YES  |     | NULL       |                |
| total_cross_conversions_basket_value        | decimal(23,8)              | YES  |     | NULL       |                |
| total_cross_conversions_num_items           | int(10) unsigned           | YES  |     | NULL       |                |
| plays                                       | int(10) unsigned           | NO   |     | 0          |                |
| abuse_play                                  | int(10) unsigned           | NO   |     | 0          |                |
| over_play                                   | int(10) unsigned           | NO   |     | 0          |                |
| new_user_play                               | int(10) unsigned           | NO   |     | 0          |                |
| play_conversions                            | int(10) unsigned           | NO   |     | 0          |                |
| total_play_conversions_basket_value         | decimal(23,8)              | YES  |     | NULL       |                |
| total_play_conversions_num_items            | int(10) unsigned           | YES  |     | NULL       |                |
| oneday_play_conversions                     | int(10) unsigned           | YES  |     | NULL       |                |
| total_oneday_play_conversions_basket_value  | decimal(23,8)              | YES  |     | NULL       |                |
| total_oneday_play_conversions_num_items     | int(10) unsigned           | YES  |     | NULL       |                |
| default_play_conversions                    | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_play_conversions_basket_value | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_play_conversions_num_items    | int(10) unsigned           | YES  |     | NULL       |                |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
59 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:53:21>DESCRIBE OPENX_V1_STATS.ox_campaign_budget_daily;
+---------------+-----------------------------+------+-----+---------------------+-------+
| Field         | Type                        | Null | Key | Default             | Extra |
+---------------+-----------------------------+------+-----+---------------------+-------+
| date_time     | datetime /* mariadb-5.3 */  | NO   | PRI | NULL                |       |
| campaignid    | mediumint(9)                | NO   | PRI | NULL                |       |
| target_budget | decimal(23,8)               | NO   |     | NULL                |       |
| updated       | timestamp /* mariadb-5.3 */ | NO   |     | current_timestamp() |       |
+---------------+-----------------------------+------+-----+---------------------+-------+
4 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:53:26>DESCRIBE OPENX_V1_STATS.ox_data_intermediate_ad_ad;
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| Field                                       | Type                       | Null | Key | Default    | Extra          |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| data_intermediate_ad_ad_id                  | bigint(20) unsigned        | NO   | PRI | NULL       | auto_increment |
| date_time                                   | datetime /* mariadb-5.3 */ | NO   | PRI | NULL       |                |
| ad_id                                       | int(10) unsigned           | NO   | MUL | NULL       |                |
| bids                                        | int(10) unsigned           | YES  |     | 0          |                |
| wins                                        | int(10) unsigned           | YES  |     | 0          |                |
| requests                                    | int(10) unsigned           | NO   |     | 0          |                |
| impressions                                 | int(10) unsigned           | NO   |     | 0          |                |
| clicks                                      | int(10) unsigned           | NO   |     | 0          |                |
| conversions                                 | int(10) unsigned           | NO   |     | 0          |                |
| total_basket_value                          | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_num_items                             | int(11)                    | YES  |     | NULL       |                |
| total_revenue                               | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_cost                                  | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_techcost                              | decimal(10,4)              | YES  |     | NULL       |                |
| updated                                     | datetime /* mariadb-5.3 */ | NO   |     | NULL       |                |
| assisted_conversions                        | int(10)                    | NO   |     | 0          |                |
| total_assisted_basket_value                 | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_assisted_num_items                    | int(10)                    | NO   |     | 0          |                |
| view_through_conversions                    | int(10)                    | NO   |     | 0          |                |
| total_view_through_basket_value             | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_view_through_num_items                | int(10)                    | NO   |     | 0          |                |
| total_rscpm                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| oneday_conversions                          | int(10)                    | NO   |     | 0          |                |
| total_oneday_basket_value                   | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_oneday_num_items                      | int(10)                    | YES  |     | 0          |                |
| total_gross                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| abuse_click                                 | int(10) unsigned           | NO   |     | 0          |                |
| over_click                                  | int(10) unsigned           | NO   |     | 0          |                |
| currency_id                                 | mediumint(9) unsigned      | NO   |     | 1          |                |
| new_user_click                              | int(10) unsigned           | YES  |     | 0          |                |
| campaignid                                  | mediumint(9) unsigned      | YES  |     | NULL       |                |
| d_type                                      | varchar(16)                | YES  |     | NULL       |                |
| c_type                                      | smallint(6) unsigned       | YES  |     | NULL       |                |
| clientid                                    | mediumint(9) unsigned      | YES  |     | NULL       |                |
| affiliateid                                 | mediumint(9) unsigned      | YES  |     | NULL       |                |
| dmp_code                                    | int(10) unsigned           | YES  |     | NULL       |                |
| dmp_sales_code                              | int(10) unsigned           | YES  |     | NULL       |                |
| total_dmp                                   | decimal(23,8)              | YES  |     | NULL       |                |
| play_impressions                            | int(10) unsigned           | YES  |     | NULL       |                |
| avg_play_time                               | bigint(20) unsigned        | YES  |     | NULL       |                |
| default_conversions                         | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_conversions_basket_value      | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_conversions_num_items         | int(10) unsigned           | YES  |     | NULL       |                |
| cross_conversions                           | int(10) unsigned           | YES  |     | NULL       |                |
| total_cross_conversions_basket_value        | decimal(23,8)              | YES  |     | NULL       |                |
| total_cross_conversions_num_items           | int(10) unsigned           | YES  |     | NULL       |                |
| plays                                       | int(10) unsigned           | NO   |     | 0          |                |
| abuse_play                                  | int(10) unsigned           | NO   |     | 0          |                |
| over_play                                   | int(10) unsigned           | NO   |     | 0          |                |
| new_user_play                               | int(10) unsigned           | NO   |     | 0          |                |
| play_conversions                            | int(10) unsigned           | NO   |     | 0          |                |
| total_play_conversions_basket_value         | decimal(23,8)              | YES  |     | NULL       |                |
| total_play_conversions_num_items            | int(10) unsigned           | YES  |     | NULL       |                |
| oneday_play_conversions                     | int(10) unsigned           | YES  |     | NULL       |                |
| total_oneday_play_conversions_basket_value  | decimal(23,8)              | YES  |     | NULL       |                |
| total_oneday_play_conversions_num_items     | int(10) unsigned           | YES  |     | NULL       |                |
| default_play_conversions                    | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_play_conversions_basket_value | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_play_conversions_num_items    | int(10) unsigned           | YES  |     | NULL       |                |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
59 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:53:32>DESCRIBE OPENX_V1_STATS.ox_data_summary_rtb_hourly_zone_ctype;
+--------------------------------------+----------------------------+------+-----+---------+----------------+
| Field                                | Type                       | Null | Key | Default | Extra          |
+--------------------------------------+----------------------------+------+-----+---------+----------------+
| data_summary_rtb_hourly_zone_type_id | bigint(20) unsigned        | NO   | PRI | NULL    | auto_increment |
| date_time                            | datetime /* mariadb-5.3 */ | NO   | PRI | NULL    |                |
| zone_id                              | int(10) unsigned           | NO   | MUL | NULL    |                |
| c_type                               | smallint(5) unsigned       | NO   | MUL | NULL    |                |
| affiliateid                          | mediumint(8) unsigned      | YES  |     | NULL    |                |
| bids                                 | int(10) unsigned           | NO   |     | 0       |                |
| requests                             | int(10) unsigned           | NO   |     | 0       |                |
| updated                              | datetime /* mariadb-5.3 */ | YES  |     | NULL    |                |
+--------------------------------------+----------------------------+------+-----+---------+----------------+
8 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:53:36>DESCRIBE OPENX_V1_STATS.ox_data_intermediate_ad_zone_ctype;
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| Field                                       | Type                       | Null | Key | Default    | Extra          |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| data_intermediate_ad_zone_ctype_id          | bigint(20) unsigned        | NO   | PRI | NULL       | auto_increment |
| date_time                                   | datetime /* mariadb-5.3 */ | NO   | PRI | NULL       |                |
| zone_id                                     | int(10) unsigned           | NO   | MUL | NULL       |                |
| c_type                                      | smallint(6) unsigned       | YES  | MUL | NULL       |                |
| bids                                        | int(10) unsigned           | YES  |     | 0          |                |
| wins                                        | int(10) unsigned           | YES  |     | 0          |                |
| requests                                    | int(10) unsigned           | NO   |     | 0          |                |
| impressions                                 | int(10) unsigned           | NO   |     | 0          |                |
| clicks                                      | int(10) unsigned           | NO   |     | 0          |                |
| conversions                                 | int(10) unsigned           | NO   |     | 0          |                |
| total_basket_value                          | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_num_items                             | int(11)                    | YES  |     | NULL       |                |
| total_revenue                               | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_cost                                  | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_techcost                              | decimal(10,4)              | YES  |     | NULL       |                |
| updated                                     | datetime /* mariadb-5.3 */ | NO   |     | NULL       |                |
| assisted_conversions                        | int(10)                    | NO   |     | 0          |                |
| total_assisted_basket_value                 | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_assisted_num_items                    | int(10)                    | NO   |     | 0          |                |
| view_through_conversions                    | int(10)                    | NO   |     | 0          |                |
| total_view_through_basket_value             | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_view_through_num_items                | int(10)                    | NO   |     | 0          |                |
| total_rscpm                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| oneday_conversions                          | int(10)                    | NO   |     | 0          |                |
| total_oneday_basket_value                   | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_oneday_num_items                      | int(10)                    | YES  |     | 0          |                |
| total_gross                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| abuse_click                                 | int(10) unsigned           | NO   |     | 0          |                |
| over_click                                  | int(10) unsigned           | NO   |     | 0          |                |
| currency_id                                 | mediumint(9) unsigned      | NO   |     | 1          |                |
| new_user_click                              | int(10) unsigned           | YES  |     | 0          |                |
| campaignid                                  | mediumint(9) unsigned      | YES  |     | NULL       |                |
| d_type                                      | varchar(16)                | YES  |     | NULL       |                |
| clientid                                    | mediumint(9) unsigned      | YES  |     | NULL       |                |
| affiliateid                                 | mediumint(9) unsigned      | YES  |     | NULL       |                |
| dmp_code                                    | int(10) unsigned           | YES  |     | NULL       |                |
| dmp_sales_code                              | int(10) unsigned           | YES  |     | NULL       |                |
| total_dmp                                   | decimal(23,8)              | YES  |     | NULL       |                |
| play_impressions                            | int(10) unsigned           | YES  |     | NULL       |                |
| avg_play_time                               | bigint(20) unsigned        | YES  |     | NULL       |                |
| default_conversions                         | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_conversions_basket_value      | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_conversions_num_items         | int(10) unsigned           | YES  |     | NULL       |                |
| cross_conversions                           | int(10) unsigned           | YES  |     | NULL       |                |
| total_cross_conversions_basket_value        | decimal(23,8)              | YES  |     | NULL       |                |
| total_cross_conversions_num_items           | int(10) unsigned           | YES  |     | NULL       |                |
| plays                                       | int(10) unsigned           | NO   |     | 0          |                |
| abuse_play                                  | int(10) unsigned           | NO   |     | 0          |                |
| over_play                                   | int(10) unsigned           | NO   |     | 0          |                |
| new_user_play                               | int(10) unsigned           | NO   |     | 0          |                |
| play_conversions                            | int(10) unsigned           | NO   |     | 0          |                |
| total_play_conversions_basket_value         | decimal(23,8)              | YES  |     | NULL       |                |
| total_play_conversions_num_items            | int(10) unsigned           | YES  |     | NULL       |                |
| oneday_play_conversions                     | int(10) unsigned           | YES  |     | NULL       |                |
| total_oneday_play_conversions_basket_value  | decimal(23,8)              | YES  |     | NULL       |                |
| total_oneday_play_conversions_num_items     | int(10) unsigned           | YES  |     | NULL       |                |
| default_play_conversions                    | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_play_conversions_basket_value | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_play_conversions_num_items    | int(10) unsigned           | YES  |     | NULL       |                |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
59 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:53:42>DESCRIBE OPENX_V1_STATS.ox_data_summary_ad_daily;
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| Field                                       | Type                       | Null | Key | Default    | Extra          |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| data_summary_ad_daily_id                    | bigint(20) unsigned        | NO   | PRI | NULL       | auto_increment |
| date_time                                   | datetime /* mariadb-5.3 */ | NO   | PRI | NULL       |                |
| ad_id                                       | int(10) unsigned           | NO   | MUL | NULL       |                |
| creative_id                                 | int(10) unsigned           | NO   |     | NULL       |                |
| zone_id                                     | int(10) unsigned           | NO   | MUL | NULL       |                |
| bids                                        | int(10) unsigned           | YES  |     | 0          |                |
| wins                                        | int(10) unsigned           | YES  |     | 0          |                |
| requests                                    | int(10) unsigned           | NO   |     | 0          |                |
| impressions                                 | int(10) unsigned           | NO   |     | 0          |                |
| clicks                                      | int(10) unsigned           | NO   |     | 0          |                |
| conversions                                 | int(10) unsigned           | NO   |     | 0          |                |
| total_basket_value                          | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_num_items                             | int(11)                    | YES  |     | NULL       |                |
| total_revenue                               | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_cost                                  | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_techcost                              | decimal(10,4)              | YES  |     | NULL       |                |
| updated                                     | datetime /* mariadb-5.3 */ | NO   |     | NULL       |                |
| assisted_conversions                        | int(10)                    | NO   |     | 0          |                |
| total_assisted_basket_value                 | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_assisted_num_items                    | int(10)                    | NO   |     | 0          |                |
| view_through_conversions                    | int(10)                    | NO   |     | 0          |                |
| total_view_through_basket_value             | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_view_through_num_items                | int(10)                    | NO   |     | 0          |                |
| total_rscpm                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| oneday_conversions                          | int(10)                    | NO   |     | 0          |                |
| total_oneday_basket_value                   | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_oneday_num_items                      | int(10)                    | YES  |     | 0          |                |
| total_gross                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| abuse_click                                 | int(10) unsigned           | NO   |     | 0          |                |
| over_click                                  | int(10) unsigned           | NO   |     | 0          |                |
| currency_id                                 | mediumint(9) unsigned      | NO   |     | 1          |                |
| new_user_click                              | int(10) unsigned           | YES  |     | 0          |                |
| campaignid                                  | mediumint(9) unsigned      | YES  |     | NULL       |                |
| d_type                                      | varchar(16)                | YES  |     | NULL       |                |
| c_type                                      | smallint(6) unsigned       | YES  |     | NULL       |                |
| clientid                                    | mediumint(9) unsigned      | YES  |     | NULL       |                |
| affiliateid                                 | mediumint(9) unsigned      | YES  |     | NULL       |                |
| dmp_code                                    | int(10) unsigned           | YES  |     | NULL       |                |
| dmp_sales_code                              | int(10) unsigned           | YES  |     | NULL       |                |
| total_dmp                                   | decimal(23,8)              | YES  |     | NULL       |                |
| play_impressions                            | int(10) unsigned           | YES  |     | NULL       |                |
| avg_play_time                               | bigint(20) unsigned        | YES  |     | NULL       |                |
| default_conversions                         | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_conversions_basket_value      | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_conversions_num_items         | int(10) unsigned           | YES  |     | NULL       |                |
| cross_conversions                           | int(10) unsigned           | YES  |     | NULL       |                |
| total_cross_conversions_basket_value        | decimal(23,8)              | YES  |     | NULL       |                |
| total_cross_conversions_num_items           | int(10) unsigned           | YES  |     | NULL       |                |
| plays                                       | int(10) unsigned           | NO   |     | 0          |                |
| abuse_play                                  | int(10) unsigned           | NO   |     | 0          |                |
| over_play                                   | int(10) unsigned           | NO   |     | 0          |                |
| new_user_play                               | int(10) unsigned           | NO   |     | 0          |                |
| play_conversions                            | int(10) unsigned           | NO   |     | 0          |                |
| total_play_conversions_basket_value         | decimal(23,8)              | YES  |     | NULL       |                |
| total_play_conversions_num_items            | int(10) unsigned           | YES  |     | NULL       |                |
| oneday_play_conversions                     | int(10) unsigned           | YES  |     | NULL       |                |
| total_oneday_play_conversions_basket_value  | decimal(23,8)              | YES  |     | NULL       |                |
| total_oneday_play_conversions_num_items     | int(10) unsigned           | YES  |     | NULL       |                |
| default_play_conversions                    | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_play_conversions_basket_value | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_play_conversions_num_items    | int(10) unsigned           | YES  |     | NULL       |                |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
61 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:53:48>DESCRIBE OPENX_V1_STATS.ox_data_summary_astg_tagging_type_stats_hourly;
+----------------------------+----------------------------+------+-----+---------------------+----------------+
| Field                      | Type                       | Null | Key | Default             | Extra          |
+----------------------------+----------------------------+------+-----+---------------------+----------------+
| astg_tagging_type_stats_id | bigint(20) unsigned        | NO   | PRI | NULL                | auto_increment |
| date_time                  | datetime /* mariadb-5.3 */ | NO   | PRI | current_timestamp() |                |
| clientid                   | mediumint(9) unsigned      | NO   |     | NULL                |                |
| type                       | varchar(80)                | YES  |     | NULL                |                |
| device_os                  | varchar(15)                | YES  |     | NULL                |                |
| cnt                        | int(10) unsigned           | NO   |     | 0                   |                |
| err_cnt                    | int(10) unsigned           | NO   |     | 0                   |                |
| mismatched_i_cnt           | int(10) unsigned           | NO   |     | 0                   |                |
| err_desc                   | text                       | YES  |     | NULL                |                |
| oaidt_s_cnt                | int(10) unsigned           | YES  |     | NULL                |                |
+----------------------------+----------------------------+------+-----+---------------------+----------------+
10 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:53:51>DESCRIBE OPENX_V1_STATS.ox_log_maintenance_priority;
+-----------------------------+----------------------------+------+-----+---------+----------------+
| Field                       | Type                       | Null | Key | Default | Extra          |
+-----------------------------+----------------------------+------+-----+---------+----------------+
| log_maintenance_priority_id | int(11)                    | NO   | PRI | NULL    | auto_increment |
| start_run                   | datetime /* mariadb-5.3 */ | NO   |     | NULL    |                |
| end_run                     | datetime /* mariadb-5.3 */ | NO   |     | NULL    |                |
| operation_interval          | int(11)                    | NO   |     | NULL    |                |
| duration                    | int(11)                    | NO   |     | NULL    |                |
| run_type                    | tinyint(3) unsigned        | NO   |     | NULL    |                |
| updated_to                  | datetime /* mariadb-5.3 */ | YES  |     | NULL    |                |
+-----------------------------+----------------------------+------+-----+---------+----------------+
7 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:53:54>DESCRIBE OPENX_V1_STATS.ox_data_all_creatives_log;
+----------------------+----------------------------+------+-----+---------+----------------+
| Field                | Type                       | Null | Key | Default | Extra          |
+----------------------+----------------------------+------+-----+---------+----------------+
| log_idx              | bigint(20)                 | NO   | PRI | NULL    | auto_increment |
| start_datetime       | datetime /* mariadb-5.3 */ | NO   | MUL | NULL    |                |
| end_datetime         | datetime /* mariadb-5.3 */ | NO   |     | NULL    |                |
| batch_status         | int(11)                    | NO   |     | 0       |                |
| batch_start_datetime | datetime /* mariadb-5.3 */ | NO   | MUL | NULL    |                |
| batch_end_datetime   | datetime /* mariadb-5.3 */ | NO   |     | NULL    |                |
+----------------------+----------------------------+------+-----+---------+----------------+
6 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:53:57>DESCRIBE OPENX_V1_STATS.ox_data_intermediate_ad;
+---------------------------------------------+----------------------------+------+-----+---------------------+----------------+
| Field                                       | Type                       | Null | Key | Default             | Extra          |
+---------------------------------------------+----------------------------+------+-----+---------------------+----------------+
| data_intermediate_ad_id                     | bigint(20) unsigned        | NO   | PRI | NULL                | auto_increment |
| date_time                                   | datetime /* mariadb-5.3 */ | NO   | PRI | NULL                |                |
| operation_interval                          | int(10) unsigned           | NO   |     | NULL                |                |
| operation_interval_id                       | int(10) unsigned           | NO   |     | NULL                |                |
| interval_start                              | datetime /* mariadb-5.3 */ | NO   | MUL | NULL                |                |
| interval_end                                | datetime /* mariadb-5.3 */ | NO   |     | NULL                |                |
| ad_id                                       | int(10) unsigned           | NO   | MUL | NULL                |                |
| creative_id                                 | int(10) unsigned           | NO   |     | NULL                |                |
| zone_id                                     | int(10) unsigned           | NO   | MUL | NULL                |                |
| bids                                        | int(10) unsigned           | YES  |     | 0                   |                |
| wins                                        | int(10) unsigned           | YES  |     | 0                   |                |
| requests                                    | int(10) unsigned           | NO   |     | 0                   |                |
| impressions                                 | int(10) unsigned           | NO   |     | 0                   |                |
| clicks                                      | int(10) unsigned           | NO   |     | 0                   |                |
| conversions                                 | int(10) unsigned           | NO   |     | 0                   |                |
| total_basket_value                          | decimal(23,8)              | YES  |     | 0.00000000          |                |
| total_num_items                             | int(11)                    | NO   |     | 0                   |                |
| updated                                     | datetime /* mariadb-5.3 */ | NO   |     | 0000-00-00 00:00:00 |                |
| total_revenue                               | decimal(23,8) unsigned     | YES  |     | 0.00000000          |                |
| assisted_conversions                        | int(10)                    | NO   |     | 0                   |                |
| total_assisted_basket_value                 | decimal(23,8)              | YES  |     | 0.00000000          |                |
| total_assisted_num_items                    | int(10)                    | NO   |     | 0                   |                |
| view_through_conversions                    | int(10)                    | NO   |     | 0                   |                |
| total_view_through_basket_value             | decimal(23,8)              | YES  |     | 0.00000000          |                |
| total_view_through_num_items                | int(10)                    | NO   |     | 0                   |                |
| total_rscpm                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000          |                |
| oneday_conversions                          | int(10)                    | NO   |     | 0                   |                |
| total_oneday_basket_value                   | decimal(23,8)              | YES  |     | 0.00000000          |                |
| total_oneday_num_items                      | int(10)                    | YES  |     | 0                   |                |
| total_gross                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000          |                |
| bucket_id                                   | smallint(6)                | NO   | MUL | 0                   |                |
| abuse_click                                 | int(10)                    | NO   |     | 0                   |                |
| over_click                                  | int(10)                    | NO   |     | 0                   |                |
| currency_id                                 | mediumint(9) unsigned      | NO   |     | 1                   |                |
| new_user_click                              | int(10) unsigned           | NO   |     | 0                   |                |
| campaignid                                  | mediumint(9) unsigned      | YES  |     | NULL                |                |
| d_type                                      | varchar(16)                | YES  |     | NULL                |                |
| c_type                                      | smallint(6) unsigned       | YES  |     | NULL                |                |
| clientid                                    | mediumint(9) unsigned      | YES  |     | NULL                |                |
| affiliateid                                 | mediumint(9) unsigned      | YES  |     | NULL                |                |
| dmp_code                                    | int(10) unsigned           | YES  |     | NULL                |                |
| dmp_sales_code                              | int(10) unsigned           | YES  |     | NULL                |                |
| total_dmp                                   | decimal(23,8)              | YES  |     | NULL                |                |
| play_impressions                            | int(10) unsigned           | YES  |     | NULL                |                |
| avg_play_time                               | bigint(20) unsigned        | YES  |     | NULL                |                |
| default_conversions                         | int(10) unsigned           | YES  |     | NULL                |                |
| total_default_conversions_basket_value      | decimal(23,8)              | YES  |     | NULL                |                |
| total_default_conversions_num_items         | int(10) unsigned           | YES  |     | NULL                |                |
| cross_conversions                           | int(10) unsigned           | YES  |     | NULL                |                |
| total_cross_conversions_basket_value        | decimal(23,8)              | YES  |     | NULL                |                |
| total_cross_conversions_num_items           | int(10) unsigned           | YES  |     | NULL                |                |
| plays                                       | int(10) unsigned           | NO   |     | 0                   |                |
| abuse_play                                  | int(10) unsigned           | NO   |     | 0                   |                |
| over_play                                   | int(10) unsigned           | NO   |     | 0                   |                |
| new_user_play                               | int(10) unsigned           | NO   |     | 0                   |                |
| play_conversions                            | int(10) unsigned           | NO   |     | 0                   |                |
| total_play_conversions_basket_value         | decimal(23,8)              | YES  |     | NULL                |                |
| total_play_conversions_num_items            | int(10) unsigned           | YES  |     | NULL                |                |
| oneday_play_conversions                     | int(10) unsigned           | YES  |     | NULL                |                |
| total_oneday_play_conversions_basket_value  | decimal(23,8)              | YES  |     | NULL                |                |
| total_oneday_play_conversions_num_items     | int(10) unsigned           | YES  |     | NULL                |                |
| default_play_conversions                    | int(10) unsigned           | YES  |     | NULL                |                |
| total_default_play_conversions_basket_value | decimal(23,8)              | YES  |     | NULL                |                |
| total_default_play_conversions_num_items    | int(10) unsigned           | YES  |     | NULL                |                |
+---------------------------------------------+----------------------------+------+-----+---------------------+----------------+
64 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:54:03>DESCRIBE OPENX_V1_STATS.ox_log_maintenance_statistics;
+-------------------------------+----------------------------+------+-----+---------+----------------+
| Field                         | Type                       | Null | Key | Default | Extra          |
+-------------------------------+----------------------------+------+-----+---------+----------------+
| log_maintenance_statistics_id | int(11)                    | NO   | PRI | NULL    | auto_increment |
| start_run                     | datetime /* mariadb-5.3 */ | NO   |     | NULL    |                |
| end_run                       | datetime /* mariadb-5.3 */ | NO   | MUL | NULL    |                |
| duration                      | int(11)                    | NO   |     | NULL    |                |
| adserver_run_type             | int(2)                     | YES  |     | NULL    |                |
| search_run_type               | int(2)                     | YES  |     | NULL    |                |
| tracker_run_type              | int(2)                     | YES  |     | NULL    |                |
| updated_to                    | datetime /* mariadb-5.3 */ | YES  |     | NULL    |                |
+-------------------------------+----------------------------+------+-----+---------+----------------+
8 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:54:07>DESCRIBE OPENX_V1_STATS.ox_data_summary_ad_daily_ad;
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| Field                                       | Type                       | Null | Key | Default    | Extra          |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| data_summary_ad_daily_ad_id                 | bigint(20) unsigned        | NO   | PRI | NULL       | auto_increment |
| date_time                                   | datetime /* mariadb-5.3 */ | NO   | PRI | NULL       |                |
| ad_id                                       | int(10) unsigned           | NO   | MUL | NULL       |                |
| bids                                        | int(10) unsigned           | YES  |     | 0          |                |
| wins                                        | int(10) unsigned           | YES  |     | 0          |                |
| requests                                    | int(10) unsigned           | NO   |     | 0          |                |
| impressions                                 | int(10) unsigned           | NO   |     | 0          |                |
| clicks                                      | int(10) unsigned           | NO   |     | 0          |                |
| conversions                                 | int(10) unsigned           | NO   |     | 0          |                |
| total_basket_value                          | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_num_items                             | int(11)                    | YES  |     | NULL       |                |
| total_revenue                               | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_cost                                  | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_techcost                              | decimal(10,4)              | YES  |     | NULL       |                |
| updated                                     | datetime /* mariadb-5.3 */ | NO   |     | NULL       |                |
| assisted_conversions                        | int(10)                    | NO   |     | 0          |                |
| total_assisted_basket_value                 | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_assisted_num_items                    | int(10)                    | NO   |     | 0          |                |
| view_through_conversions                    | int(10)                    | NO   |     | 0          |                |
| total_view_through_basket_value             | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_view_through_num_items                | int(10)                    | NO   |     | 0          |                |
| total_rscpm                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| oneday_conversions                          | int(10)                    | NO   |     | 0          |                |
| total_oneday_basket_value                   | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_oneday_num_items                      | int(10)                    | YES  |     | 0          |                |
| total_gross                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| abuse_click                                 | int(10) unsigned           | NO   |     | 0          |                |
| over_click                                  | int(10) unsigned           | NO   |     | 0          |                |
| currency_id                                 | mediumint(9) unsigned      | NO   |     | 1          |                |
| new_user_click                              | int(10) unsigned           | YES  |     | 0          |                |
| campaignid                                  | mediumint(9) unsigned      | YES  |     | NULL       |                |
| d_type                                      | varchar(16)                | YES  |     | NULL       |                |
| c_type                                      | smallint(6) unsigned       | YES  |     | NULL       |                |
| clientid                                    | mediumint(9) unsigned      | YES  |     | NULL       |                |
| affiliateid                                 | mediumint(9) unsigned      | YES  |     | NULL       |                |
| dmp_code                                    | int(10) unsigned           | YES  |     | NULL       |                |
| dmp_sales_code                              | int(10) unsigned           | YES  |     | NULL       |                |
| total_dmp                                   | decimal(23,8)              | YES  |     | NULL       |                |
| play_impressions                            | int(10) unsigned           | YES  |     | NULL       |                |
| avg_play_time                               | bigint(20) unsigned        | YES  |     | NULL       |                |
| default_conversions                         | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_conversions_basket_value      | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_conversions_num_items         | int(10) unsigned           | YES  |     | NULL       |                |
| cross_conversions                           | int(10) unsigned           | YES  |     | NULL       |                |
| total_cross_conversions_basket_value        | decimal(23,8)              | YES  |     | NULL       |                |
| total_cross_conversions_num_items           | int(10) unsigned           | YES  |     | NULL       |                |
| plays                                       | int(10) unsigned           | NO   |     | 0          |                |
| abuse_play                                  | int(10) unsigned           | NO   |     | 0          |                |
| over_play                                   | int(10) unsigned           | NO   |     | 0          |                |
| new_user_play                               | int(10) unsigned           | NO   |     | 0          |                |
| play_conversions                            | int(10) unsigned           | NO   |     | 0          |                |
| total_play_conversions_basket_value         | decimal(23,8)              | YES  |     | NULL       |                |
| total_play_conversions_num_items            | int(10) unsigned           | YES  |     | NULL       |                |
| oneday_play_conversions                     | int(10) unsigned           | YES  |     | NULL       |                |
| total_oneday_play_conversions_basket_value  | decimal(23,8)              | YES  |     | NULL       |                |
| total_oneday_play_conversions_num_items     | int(10) unsigned           | YES  |     | NULL       |                |
| default_play_conversions                    | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_play_conversions_basket_value | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_play_conversions_num_items    | int(10) unsigned           | YES  |     | NULL       |                |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
59 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:54:12>DESCRIBE OPENX_V1_STATS.ox_data_summary_rtb_daily_campaign;
+------------------------------------+----------------------------+------+-----+---------+----------------+
| Field                              | Type                       | Null | Key | Default | Extra          |
+------------------------------------+----------------------------+------+-----+---------+----------------+
| data_summary_rtb_daily_campaign_id | bigint(20) unsigned        | NO   | PRI | NULL    | auto_increment |
| date_time                          | datetime /* mariadb-5.3 */ | NO   | PRI | NULL    |                |
| campaignid                         | mediumint(8) unsigned      | NO   | MUL | NULL    |                |
| c_type                             | smallint(5) unsigned       | NO   |     | NULL    |                |
| d_type                             | varchar(16)                | YES  |     | NULL    |                |
| clientid                           | mediumint(8) unsigned      | YES  | MUL | NULL    |                |
| bids                               | int(10) unsigned           | NO   |     | 0       |                |
| requests                           | int(10) unsigned           | NO   |     | 0       |                |
| updated                            | datetime /* mariadb-5.3 */ | YES  |     | NULL    |                |
+------------------------------------+----------------------------+------+-----+---------+----------------+
9 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:54:20>DESCRIBE OPENX_V1_STATS.ox_data_summary_rtb_hourly_ad;
+-------------------------------+----------------------------+------+-----+---------+----------------+
| Field                         | Type                       | Null | Key | Default | Extra          |
+-------------------------------+----------------------------+------+-----+---------+----------------+
| data_summary_rtb_hourly_ad_id | bigint(20) unsigned        | NO   | PRI | NULL    | auto_increment |
| date_time                     | datetime /* mariadb-5.3 */ | NO   | PRI | NULL    |                |
| ad_id                         | int(10) unsigned           | NO   | MUL | NULL    |                |
| campaignid                    | mediumint(8) unsigned      | NO   |     | NULL    |                |
| c_type                        | smallint(5) unsigned       | NO   |     | NULL    |                |
| d_type                        | varchar(16)                | YES  |     | NULL    |                |
| clientid                      | mediumint(8) unsigned      | YES  | MUL | NULL    |                |
| bids                          | int(10) unsigned           | NO   |     | 0       |                |
| requests                      | int(10) unsigned           | NO   |     | 0       |                |
| updated                       | datetime /* mariadb-5.3 */ | YES  |     | NULL    |                |
+-------------------------------+----------------------------+------+-----+---------+----------------+
10 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:54:28>DESCRIBE OPENX_V1_STATS.ox_data_summary_rtb_hourly;
+----------------------------+----------------------------+------+-----+---------+----------------+
| Field                      | Type                       | Null | Key | Default | Extra          |
+----------------------------+----------------------------+------+-----+---------+----------------+
| data_summary_rtb_hourly_id | bigint(20) unsigned        | NO   | PRI | NULL    | auto_increment |
| date_time                  | datetime /* mariadb-5.3 */ | NO   | PRI | NULL    |                |
| ad_id                      | int(10) unsigned           | NO   |     | NULL    |                |
| zone_id                    | int(10) unsigned           | NO   |     | NULL    |                |
| campaignid                 | mediumint(8) unsigned      | NO   |     | NULL    |                |
| c_type                     | smallint(5) unsigned       | NO   |     | NULL    |                |
| d_type                     | varchar(16)                | YES  |     | NULL    |                |
| clientid                   | mediumint(8) unsigned      | YES  |     | NULL    |                |
| affiliateid                | mediumint(8) unsigned      | YES  |     | NULL    |                |
| bids                       | int(10) unsigned           | NO   |     | 0       |                |
| requests                   | int(10) unsigned           | NO   |     | 0       |                |
| updated                    | datetime /* mariadb-5.3 */ | YES  |     | NULL    |                |
+----------------------------+----------------------------+------+-----+---------+----------------+
12 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:54:31>DESCRIBE OPENX_V1_STATS.ox_data_summary_ad_hourly_campaign;
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| Field                                       | Type                       | Null | Key | Default    | Extra          |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| data_summary_ad_hourly_campaign_id          | bigint(20) unsigned        | NO   | PRI | NULL       | auto_increment |
| date_time                                   | datetime /* mariadb-5.3 */ | NO   | PRI | NULL       |                |
| campaignid                                  | mediumint(9) unsigned      | NO   | MUL | NULL       |                |
| bids                                        | int(10) unsigned           | YES  |     | 0          |                |
| wins                                        | int(10) unsigned           | YES  |     | 0          |                |
| requests                                    | int(10) unsigned           | NO   |     | 0          |                |
| impressions                                 | int(10) unsigned           | NO   |     | 0          |                |
| clicks                                      | int(10) unsigned           | NO   |     | 0          |                |
| conversions                                 | int(10) unsigned           | NO   |     | 0          |                |
| total_basket_value                          | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_num_items                             | int(11)                    | YES  |     | NULL       |                |
| total_revenue                               | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_cost                                  | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_techcost                              | decimal(10,4)              | YES  |     | NULL       |                |
| updated                                     | datetime /* mariadb-5.3 */ | NO   |     | NULL       |                |
| assisted_conversions                        | int(10)                    | NO   |     | 0          |                |
| total_assisted_basket_value                 | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_assisted_num_items                    | int(10)                    | NO   |     | 0          |                |
| view_through_conversions                    | int(10)                    | NO   |     | 0          |                |
| total_view_through_basket_value             | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_view_through_num_items                | int(10)                    | NO   |     | 0          |                |
| total_rscpm                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| oneday_conversions                          | int(10)                    | NO   |     | 0          |                |
| total_oneday_basket_value                   | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_oneday_num_items                      | int(10)                    | YES  |     | 0          |                |
| total_gross                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| abuse_click                                 | int(10) unsigned           | NO   |     | 0          |                |
| over_click                                  | int(10) unsigned           | NO   |     | 0          |                |
| currency_id                                 | mediumint(9) unsigned      | NO   |     | 1          |                |
| new_user_click                              | int(10) unsigned           | YES  |     | 0          |                |
| d_type                                      | varchar(16)                | YES  |     | NULL       |                |
| c_type                                      | smallint(6) unsigned       | YES  |     | NULL       |                |
| clientid                                    | mediumint(9) unsigned      | YES  |     | NULL       |                |
| affiliateid                                 | mediumint(9) unsigned      | YES  |     | NULL       |                |
| dmp_code                                    | int(10) unsigned           | YES  |     | NULL       |                |
| dmp_sales_code                              | int(10) unsigned           | YES  |     | NULL       |                |
| total_dmp                                   | decimal(23,8)              | YES  |     | NULL       |                |
| play_impressions                            | int(10) unsigned           | YES  |     | NULL       |                |
| avg_play_time                               | bigint(20) unsigned        | YES  |     | NULL       |                |
| default_conversions                         | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_conversions_basket_value      | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_conversions_num_items         | int(10) unsigned           | YES  |     | NULL       |                |
| cross_conversions                           | int(10) unsigned           | YES  |     | NULL       |                |
| total_cross_conversions_basket_value        | decimal(23,8)              | YES  |     | NULL       |                |
| total_cross_conversions_num_items           | int(10) unsigned           | YES  |     | NULL       |                |
| plays                                       | int(10) unsigned           | NO   |     | 0          |                |
| abuse_play                                  | int(10) unsigned           | NO   |     | 0          |                |
| over_play                                   | int(10) unsigned           | NO   |     | 0          |                |
| new_user_play                               | int(10) unsigned           | NO   |     | 0          |                |
| play_conversions                            | int(10) unsigned           | NO   |     | 0          |                |
| total_play_conversions_basket_value         | decimal(23,8)              | YES  |     | NULL       |                |
| total_play_conversions_num_items            | int(10) unsigned           | YES  |     | NULL       |                |
| oneday_play_conversions                     | int(10) unsigned           | YES  |     | NULL       |                |
| total_oneday_play_conversions_basket_value  | decimal(23,8)              | YES  |     | NULL       |                |
| total_oneday_play_conversions_num_items     | int(10) unsigned           | YES  |     | NULL       |                |
| default_play_conversions                    | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_play_conversions_basket_value | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_play_conversions_num_items    | int(10) unsigned           | YES  |     | NULL       |                |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
58 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:54:35>DESCRIBE OPENX_V1_STATS.ox_data_intermediate_ad_zone;
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| Field                                       | Type                       | Null | Key | Default    | Extra          |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| data_intermediate_ad_zone_id                | bigint(20) unsigned        | NO   | PRI | NULL       | auto_increment |
| date_time                                   | datetime /* mariadb-5.3 */ | NO   | PRI | NULL       |                |
| zone_id                                     | int(10) unsigned           | NO   | MUL | NULL       |                |
| bids                                        | int(10) unsigned           | YES  |     | 0          |                |
| wins                                        | int(10) unsigned           | YES  |     | 0          |                |
| requests                                    | int(10) unsigned           | NO   |     | 0          |                |
| impressions                                 | int(10) unsigned           | NO   |     | 0          |                |
| clicks                                      | int(10) unsigned           | NO   |     | 0          |                |
| conversions                                 | int(10) unsigned           | NO   |     | 0          |                |
| total_basket_value                          | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_num_items                             | int(11)                    | YES  |     | NULL       |                |
| total_revenue                               | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_cost                                  | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_techcost                              | decimal(10,4)              | YES  |     | NULL       |                |
| updated                                     | datetime /* mariadb-5.3 */ | NO   |     | NULL       |                |
| assisted_conversions                        | int(10)                    | NO   |     | 0          |                |
| total_assisted_basket_value                 | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_assisted_num_items                    | int(10)                    | NO   |     | 0          |                |
| view_through_conversions                    | int(10)                    | NO   |     | 0          |                |
| total_view_through_basket_value             | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_view_through_num_items                | int(10)                    | NO   |     | 0          |                |
| total_rscpm                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| oneday_conversions                          | int(10)                    | NO   |     | 0          |                |
| total_oneday_basket_value                   | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_oneday_num_items                      | int(10)                    | YES  |     | 0          |                |
| total_gross                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| abuse_click                                 | int(10) unsigned           | NO   |     | 0          |                |
| over_click                                  | int(10) unsigned           | NO   |     | 0          |                |
| currency_id                                 | mediumint(9) unsigned      | NO   |     | 1          |                |
| new_user_click                              | int(10) unsigned           | YES  |     | 0          |                |
| campaignid                                  | mediumint(9) unsigned      | YES  |     | NULL       |                |
| d_type                                      | varchar(16)                | YES  |     | NULL       |                |
| c_type                                      | smallint(6) unsigned       | YES  |     | NULL       |                |
| clientid                                    | mediumint(9) unsigned      | YES  |     | NULL       |                |
| affiliateid                                 | mediumint(9) unsigned      | YES  |     | NULL       |                |
| dmp_code                                    | int(10) unsigned           | YES  |     | NULL       |                |
| dmp_sales_code                              | int(10) unsigned           | YES  |     | NULL       |                |
| total_dmp                                   | decimal(23,8)              | YES  |     | NULL       |                |
| play_impressions                            | int(10) unsigned           | YES  |     | NULL       |                |
| avg_play_time                               | bigint(20) unsigned        | YES  |     | NULL       |                |
| default_conversions                         | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_conversions_basket_value      | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_conversions_num_items         | int(10) unsigned           | YES  |     | NULL       |                |
| cross_conversions                           | int(10) unsigned           | YES  |     | NULL       |                |
| total_cross_conversions_basket_value        | decimal(23,8)              | YES  |     | NULL       |                |
| total_cross_conversions_num_items           | int(10) unsigned           | YES  |     | NULL       |                |
| plays                                       | int(10) unsigned           | NO   |     | 0          |                |
| abuse_play                                  | int(10) unsigned           | NO   |     | 0          |                |
| over_play                                   | int(10) unsigned           | NO   |     | 0          |                |
| new_user_play                               | int(10) unsigned           | NO   |     | 0          |                |
| play_conversions                            | int(10) unsigned           | NO   |     | 0          |                |
| total_play_conversions_basket_value         | decimal(23,8)              | YES  |     | NULL       |                |
| total_play_conversions_num_items            | int(10) unsigned           | YES  |     | NULL       |                |
| oneday_play_conversions                     | int(10) unsigned           | YES  |     | NULL       |                |
| total_oneday_play_conversions_basket_value  | decimal(23,8)              | YES  |     | NULL       |                |
| total_oneday_play_conversions_num_items     | int(10) unsigned           | YES  |     | NULL       |                |
| default_play_conversions                    | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_play_conversions_basket_value | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_play_conversions_num_items    | int(10) unsigned           | YES  |     | NULL       |                |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
59 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:54:43>DESCRIBE OPENX_V1_STATS.ox_data_summary_ad_hourly_zone_ctype;
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| Field                                       | Type                       | Null | Key | Default    | Extra          |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| data_summary_ad_hourly_zone_ctype_id        | bigint(20) unsigned        | NO   | PRI | NULL       | auto_increment |
| date_time                                   | datetime /* mariadb-5.3 */ | NO   | PRI | NULL       |                |
| zone_id                                     | int(10) unsigned           | NO   | MUL | NULL       |                |
| c_type                                      | smallint(6) unsigned       | YES  | MUL | NULL       |                |
| bids                                        | int(10) unsigned           | YES  |     | 0          |                |
| wins                                        | int(10) unsigned           | YES  |     | 0          |                |
| requests                                    | int(10) unsigned           | NO   |     | 0          |                |
| impressions                                 | int(10) unsigned           | NO   |     | 0          |                |
| clicks                                      | int(10) unsigned           | NO   |     | 0          |                |
| conversions                                 | int(10) unsigned           | NO   |     | 0          |                |
| total_basket_value                          | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_num_items                             | int(11)                    | YES  |     | NULL       |                |
| total_revenue                               | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_cost                                  | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_techcost                              | decimal(10,4)              | YES  |     | NULL       |                |
| updated                                     | datetime /* mariadb-5.3 */ | NO   |     | NULL       |                |
| assisted_conversions                        | int(10)                    | NO   |     | 0          |                |
| total_assisted_basket_value                 | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_assisted_num_items                    | int(10)                    | NO   |     | 0          |                |
| view_through_conversions                    | int(10)                    | NO   |     | 0          |                |
| total_view_through_basket_value             | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_view_through_num_items                | int(10)                    | NO   |     | 0          |                |
| total_rscpm                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| oneday_conversions                          | int(10)                    | NO   |     | 0          |                |
| total_oneday_basket_value                   | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_oneday_num_items                      | int(10)                    | YES  |     | 0          |                |
| total_gross                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| abuse_click                                 | int(10) unsigned           | NO   |     | 0          |                |
| over_click                                  | int(10) unsigned           | NO   |     | 0          |                |
| currency_id                                 | mediumint(9) unsigned      | NO   |     | 1          |                |
| new_user_click                              | int(10) unsigned           | YES  |     | 0          |                |
| campaignid                                  | mediumint(9) unsigned      | YES  |     | NULL       |                |
| d_type                                      | varchar(16)                | YES  |     | NULL       |                |
| clientid                                    | mediumint(9) unsigned      | YES  |     | NULL       |                |
| affiliateid                                 | mediumint(9) unsigned      | YES  |     | NULL       |                |
| dmp_code                                    | int(10) unsigned           | YES  |     | NULL       |                |
| dmp_sales_code                              | int(10) unsigned           | YES  |     | NULL       |                |
| total_dmp                                   | decimal(23,8)              | YES  |     | NULL       |                |
| play_impressions                            | int(10) unsigned           | YES  |     | NULL       |                |
| avg_play_time                               | bigint(20) unsigned        | YES  |     | NULL       |                |
| default_conversions                         | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_conversions_basket_value      | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_conversions_num_items         | int(10) unsigned           | YES  |     | NULL       |                |
| cross_conversions                           | int(10) unsigned           | YES  |     | NULL       |                |
| total_cross_conversions_basket_value        | decimal(23,8)              | YES  |     | NULL       |                |
| total_cross_conversions_num_items           | int(10) unsigned           | YES  |     | NULL       |                |
| plays                                       | int(10) unsigned           | NO   |     | 0          |                |
| abuse_play                                  | int(10) unsigned           | NO   |     | 0          |                |
| over_play                                   | int(10) unsigned           | NO   |     | 0          |                |
| new_user_play                               | int(10) unsigned           | NO   |     | 0          |                |
| play_conversions                            | int(10) unsigned           | NO   |     | 0          |                |
| total_play_conversions_basket_value         | decimal(23,8)              | YES  |     | NULL       |                |
| total_play_conversions_num_items            | int(10) unsigned           | YES  |     | NULL       |                |
| oneday_play_conversions                     | int(10) unsigned           | YES  |     | NULL       |                |
| total_oneday_play_conversions_basket_value  | decimal(23,8)              | YES  |     | NULL       |                |
| total_oneday_play_conversions_num_items     | int(10) unsigned           | YES  |     | NULL       |                |
| default_play_conversions                    | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_play_conversions_basket_value | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_play_conversions_num_items    | int(10) unsigned           | YES  |     | NULL       |                |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
59 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:55:00>DESCRIBE OPENX_V1_STATS.ox_wp_data_raw_a_item;
+--------------------+-----------------------+------+-----+------------+----------------+
| Field              | Type                  | Null | Key | Default    | Extra          |
+--------------------+-----------------------+------+-----+------------+----------------+
| conversion_item_id | bigint(20) unsigned   | NO   | PRI | NULL       | auto_increment |
| server_ip          | varchar(40)           | NO   | PRI |            |                |
| date_time          | datetime              | NO   | PRI | NULL       |                |
| action_date_time   | datetime              | NO   |     | NULL       |                |
| creative_id        | mediumint(9) unsigned | NO   | MUL | NULL       |                |
| zone_id            | mediumint(9) unsigned | NO   | MUL | NULL       |                |
| ip_address         | varchar(40)           | NO   |     | NULL       |                |
| map_id             | text                  | YES  |     | NULL       |                |
| basket_value       | decimal(23,8)         | NO   |     | 0.00000000 |                |
| num_items          | int(10) unsigned      | NO   |     | 1          |                |
| oaid               | varchar(50)           | YES  |     | NULL       |                |
| title              | text                  | YES  |     | NULL       |                |
| order_code         | varchar(256)          | YES  |     | NULL       |                |
| inside_window      | tinyint(1)            | YES  |     | 0          |                |
| currency_id        | mediumint(9) unsigned | NO   |     | 1          |                |
| event_type         | varchar(20)           | YES  |     | NULL       |                |
| conversion_id      | bigint(20) unsigned   | YES  |     | NULL       |                |
+--------------------+-----------------------+------+-----+------------+----------------+
17 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:55:14>DESCRIBE OPENX_V1_STATS.ox_data_summary_rtb_daily_zone_ctype;
+-------------------------------------+----------------------------+------+-----+---------+----------------+
| Field                               | Type                       | Null | Key | Default | Extra          |
+-------------------------------------+----------------------------+------+-----+---------+----------------+
| data_summary_rtb_daily_zone_type_id | bigint(20) unsigned        | NO   | PRI | NULL    | auto_increment |
| date_time                           | datetime /* mariadb-5.3 */ | NO   | PRI | NULL    |                |
| zone_id                             | int(10) unsigned           | NO   | MUL | NULL    |                |
| c_type                              | smallint(5) unsigned       | NO   | MUL | NULL    |                |
| affiliateid                         | mediumint(8) unsigned      | YES  |     | NULL    |                |
| bids                                | int(10) unsigned           | NO   |     | 0       |                |
| requests                            | int(10) unsigned           | NO   |     | 0       |                |
| updated                             | datetime /* mariadb-5.3 */ | YES  |     | NULL    |                |
+-------------------------------------+----------------------------+------+-----+---------+----------------+
8 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:55:27>DESCRIBE OPENX_V1_STATS.ox_data_trend_zone;
+--------------------+----------------------------+------+-----+---------+----------------+
| Field              | Type                       | Null | Key | Default | Extra          |
+--------------------+----------------------------+------+-----+---------+----------------+
| data_trend_zone_id | bigint(20)                 | NO   | PRI | NULL    | auto_increment |
| date_time          | datetime /* mariadb-5.3 */ | NO   | PRI | NULL    |                |
| interval_start     | datetime /* mariadb-5.3 */ | NO   |     | NULL    |                |
| interval_end       | datetime /* mariadb-5.3 */ | NO   |     | NULL    |                |
| zone_id            | int(10) unsigned           | NO   | MUL | NULL    |                |
| requests           | int(10) unsigned           | NO   |     | 0       |                |
| impressions        | int(10) unsigned           | NO   |     | 0       |                |
| clicks             | int(10) unsigned           | NO   |     | 0       |                |
+--------------------+----------------------------+------+-----+---------+----------------+
8 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:55:31>DESCRIBE OPENX_V1_STATS.ox_wp_data_raw_vc_item;
+--------------------+-----------------------+------+-----+------------+----------------+
| Field              | Type                  | Null | Key | Default    | Extra          |
+--------------------+-----------------------+------+-----+------------+----------------+
| conversion_item_id | bigint(20) unsigned   | NO   | PRI | NULL       | auto_increment |
| server_ip          | varchar(40)           | NO   | PRI |            |                |
| date_time          | datetime              | NO   | PRI | NULL       |                |
| action_date_time   | datetime              | NO   |     | NULL       |                |
| creative_id        | mediumint(9) unsigned | NO   | MUL | NULL       |                |
| zone_id            | mediumint(9) unsigned | NO   | MUL | NULL       |                |
| ip_address         | varchar(40)           | NO   |     | NULL       |                |
| map_id             | text                  | YES  |     | NULL       |                |
| basket_value       | decimal(23,8)         | NO   |     | 0.00000000 |                |
| num_items          | int(10) unsigned      | NO   |     | 1          |                |
| oaid               | varchar(50)           | YES  |     | NULL       |                |
| title              | text                  | YES  |     | NULL       |                |
| order_code         | varchar(256)          | YES  |     | NULL       |                |
| inside_window      | tinyint(1)            | YES  |     | 0          |                |
| currency_id        | mediumint(9) unsigned | NO   |     | 1          |                |
| event_type         | varchar(20)           | YES  |     | NULL       |                |
| conversion_id      | bigint(20) unsigned   | YES  |     | NULL       |                |
+--------------------+-----------------------+------+-----+------------+----------------+
17 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:55:35>DESCRIBE OPENX_V1_STATS.ox_data_summary_ad_daily_zone;
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| Field                                       | Type                       | Null | Key | Default    | Extra          |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| data_summary_ad_daily_zone_id               | bigint(20) unsigned        | NO   | PRI | NULL       | auto_increment |
| date_time                                   | datetime /* mariadb-5.3 */ | NO   | PRI | NULL       |                |
| zone_id                                     | int(10) unsigned           | NO   | MUL | NULL       |                |
| bids                                        | int(10) unsigned           | YES  |     | 0          |                |
| wins                                        | int(10) unsigned           | YES  |     | 0          |                |
| requests                                    | int(10) unsigned           | NO   |     | 0          |                |
| impressions                                 | int(10) unsigned           | NO   |     | 0          |                |
| clicks                                      | int(10) unsigned           | NO   |     | 0          |                |
| conversions                                 | int(10) unsigned           | NO   |     | 0          |                |
| total_basket_value                          | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_num_items                             | int(11)                    | YES  |     | NULL       |                |
| total_revenue                               | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_cost                                  | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_techcost                              | decimal(10,4)              | YES  |     | NULL       |                |
| updated                                     | datetime /* mariadb-5.3 */ | NO   |     | NULL       |                |
| assisted_conversions                        | int(10)                    | NO   |     | 0          |                |
| total_assisted_basket_value                 | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_assisted_num_items                    | int(10)                    | NO   |     | 0          |                |
| view_through_conversions                    | int(10)                    | NO   |     | 0          |                |
| total_view_through_basket_value             | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_view_through_num_items                | int(10)                    | NO   |     | 0          |                |
| total_rscpm                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| oneday_conversions                          | int(10)                    | NO   |     | 0          |                |
| total_oneday_basket_value                   | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_oneday_num_items                      | int(10)                    | YES  |     | 0          |                |
| total_gross                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| abuse_click                                 | int(10) unsigned           | NO   |     | 0          |                |
| over_click                                  | int(10) unsigned           | NO   |     | 0          |                |
| currency_id                                 | mediumint(9) unsigned      | NO   |     | 1          |                |
| new_user_click                              | int(10) unsigned           | YES  |     | 0          |                |
| campaignid                                  | mediumint(9) unsigned      | YES  |     | NULL       |                |
| d_type                                      | varchar(16)                | YES  |     | NULL       |                |
| c_type                                      | smallint(6) unsigned       | YES  |     | NULL       |                |
| clientid                                    | mediumint(9) unsigned      | YES  |     | NULL       |                |
| affiliateid                                 | mediumint(9) unsigned      | YES  |     | NULL       |                |
| dmp_code                                    | int(10) unsigned           | YES  |     | NULL       |                |
| dmp_sales_code                              | int(10) unsigned           | YES  |     | NULL       |                |
| total_dmp                                   | decimal(23,8)              | YES  |     | NULL       |                |
| play_impressions                            | int(10) unsigned           | YES  |     | NULL       |                |
| avg_play_time                               | bigint(20) unsigned        | YES  |     | NULL       |                |
| default_conversions                         | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_conversions_basket_value      | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_conversions_num_items         | int(10) unsigned           | YES  |     | NULL       |                |
| cross_conversions                           | int(10) unsigned           | YES  |     | NULL       |                |
| total_cross_conversions_basket_value        | decimal(23,8)              | YES  |     | NULL       |                |
| total_cross_conversions_num_items           | int(10) unsigned           | YES  |     | NULL       |                |
| plays                                       | int(10) unsigned           | NO   |     | 0          |                |
| abuse_play                                  | int(10) unsigned           | NO   |     | 0          |                |
| over_play                                   | int(10) unsigned           | NO   |     | 0          |                |
| new_user_play                               | int(10) unsigned           | NO   |     | 0          |                |
| play_conversions                            | int(10) unsigned           | NO   |     | 0          |                |
| total_play_conversions_basket_value         | decimal(23,8)              | YES  |     | NULL       |                |
| total_play_conversions_num_items            | int(10) unsigned           | YES  |     | NULL       |                |
| oneday_play_conversions                     | int(10) unsigned           | YES  |     | NULL       |                |
| total_oneday_play_conversions_basket_value  | decimal(23,8)              | YES  |     | NULL       |                |
| total_oneday_play_conversions_num_items     | int(10) unsigned           | YES  |     | NULL       |                |
| default_play_conversions                    | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_play_conversions_basket_value | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_play_conversions_num_items    | int(10) unsigned           | YES  |     | NULL       |                |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
59 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:55:44>DESCRIBE OPENX_V1_STATS.ox_data_summary_ad_daily_zone_ctype;
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| Field                                       | Type                       | Null | Key | Default    | Extra          |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| data_summary_ad_daily_zone_ctype_id         | bigint(20) unsigned        | NO   | PRI | NULL       | auto_increment |
| date_time                                   | datetime /* mariadb-5.3 */ | NO   | PRI | NULL       |                |
| zone_id                                     | int(10) unsigned           | NO   | MUL | NULL       |                |
| c_type                                      | smallint(6) unsigned       | YES  | MUL | NULL       |                |
| bids                                        | int(10) unsigned           | YES  |     | 0          |                |
| wins                                        | int(10) unsigned           | YES  |     | 0          |                |
| requests                                    | int(10) unsigned           | NO   |     | 0          |                |
| impressions                                 | int(10) unsigned           | NO   |     | 0          |                |
| clicks                                      | int(10) unsigned           | NO   |     | 0          |                |
| conversions                                 | int(10) unsigned           | NO   |     | 0          |                |
| total_basket_value                          | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_num_items                             | int(11)                    | YES  |     | NULL       |                |
| total_revenue                               | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_cost                                  | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_techcost                              | decimal(10,4)              | YES  |     | NULL       |                |
| updated                                     | datetime /* mariadb-5.3 */ | NO   |     | NULL       |                |
| assisted_conversions                        | int(10)                    | NO   |     | 0          |                |
| total_assisted_basket_value                 | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_assisted_num_items                    | int(10)                    | NO   |     | 0          |                |
| view_through_conversions                    | int(10)                    | NO   |     | 0          |                |
| total_view_through_basket_value             | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_view_through_num_items                | int(10)                    | NO   |     | 0          |                |
| total_rscpm                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| oneday_conversions                          | int(10)                    | NO   |     | 0          |                |
| total_oneday_basket_value                   | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_oneday_num_items                      | int(10)                    | YES  |     | 0          |                |
| total_gross                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| abuse_click                                 | int(10) unsigned           | NO   |     | 0          |                |
| over_click                                  | int(10) unsigned           | NO   |     | 0          |                |
| currency_id                                 | mediumint(9) unsigned      | NO   |     | 1          |                |
| new_user_click                              | int(10) unsigned           | YES  |     | 0          |                |
| campaignid                                  | mediumint(9) unsigned      | YES  |     | NULL       |                |
| d_type                                      | varchar(16)                | YES  |     | NULL       |                |
| clientid                                    | mediumint(9) unsigned      | YES  |     | NULL       |                |
| affiliateid                                 | mediumint(9) unsigned      | YES  |     | NULL       |                |
| dmp_code                                    | int(10) unsigned           | YES  |     | NULL       |                |
| dmp_sales_code                              | int(10) unsigned           | YES  |     | NULL       |                |
| total_dmp                                   | decimal(23,8)              | YES  |     | NULL       |                |
| play_impressions                            | int(10) unsigned           | YES  |     | NULL       |                |
| avg_play_time                               | bigint(20) unsigned        | YES  |     | NULL       |                |
| default_conversions                         | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_conversions_basket_value      | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_conversions_num_items         | int(10) unsigned           | YES  |     | NULL       |                |
| cross_conversions                           | int(10) unsigned           | YES  |     | NULL       |                |
| total_cross_conversions_basket_value        | decimal(23,8)              | YES  |     | NULL       |                |
| total_cross_conversions_num_items           | int(10) unsigned           | YES  |     | NULL       |                |
| plays                                       | int(10) unsigned           | NO   |     | 0          |                |
| abuse_play                                  | int(10) unsigned           | NO   |     | 0          |                |
| over_play                                   | int(10) unsigned           | NO   |     | 0          |                |
| new_user_play                               | int(10) unsigned           | NO   |     | 0          |                |
| play_conversions                            | int(10) unsigned           | NO   |     | 0          |                |
| total_play_conversions_basket_value         | decimal(23,8)              | YES  |     | NULL       |                |
| total_play_conversions_num_items            | int(10) unsigned           | YES  |     | NULL       |                |
| oneday_play_conversions                     | int(10) unsigned           | YES  |     | NULL       |                |
| total_oneday_play_conversions_basket_value  | decimal(23,8)              | YES  |     | NULL       |                |
| total_oneday_play_conversions_num_items     | int(10) unsigned           | YES  |     | NULL       |                |
| default_play_conversions                    | int(10) unsigned           | YES  |     | NULL       |                |
| total_default_play_conversions_basket_value | decimal(23,8)              | YES  |     | NULL       |                |
| total_default_play_conversions_num_items    | int(10) unsigned           | YES  |     | NULL       |                |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
59 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:55:49>DESCRIBE OPENX_V1_STATS.ox_wp_data_raw_ac_item;
+--------------------+----------------------------+------+-----+------------+----------------+
| Field              | Type                       | Null | Key | Default    | Extra          |
+--------------------+----------------------------+------+-----+------------+----------------+
| conversion_item_id | bigint(20) unsigned        | NO   | PRI | NULL       | auto_increment |
| server_ip          | varchar(40)                | NO   | PRI |            |                |
| date_time          | datetime /* mariadb-5.3 */ | NO   | MUL | NULL       |                |
| action_date_time   | datetime /* mariadb-5.3 */ | NO   |     | NULL       |                |
| creative_id        | mediumint(9) unsigned      | NO   | MUL | NULL       |                |
| zone_id            | mediumint(9) unsigned      | NO   | MUL | NULL       |                |
| ip_address         | varchar(40)                | NO   |     | NULL       |                |
| map_id             | text                       | YES  |     | NULL       |                |
| basket_value       | decimal(23,8)              | NO   |     | 0.00000000 |                |
| num_items          | int(10) unsigned           | NO   |     | 1          |                |
| oaid               | varchar(50)                | YES  |     | NULL       |                |
| title              | text                       | YES  |     | NULL       |                |
| order_code         | varchar(256)               | YES  |     | NULL       |                |
| inside_window      | tinyint(1)                 | YES  |     | 0          |                |
| currency_id        | mediumint(9) unsigned      | NO   |     | 1          |                |
| event_type         | varchar(20)                | YES  |     | NULL       |                |
| conversion_id      | bigint(20) unsigned        | YES  |     | NULL       |                |
+--------------------+----------------------------+------+-----+------------+----------------+
17 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:55:52>DESCRIBE OPENX_V1_STATS.ox_data_summary_rtb_hourly_campaign;
+-------------------------------------+----------------------------+------+-----+---------+----------------+
| Field                               | Type                       | Null | Key | Default | Extra          |
+-------------------------------------+----------------------------+------+-----+---------+----------------+
| data_summary_rtb_hourly_campaign_id | bigint(20) unsigned        | NO   | PRI | NULL    | auto_increment |
| date_time                           | datetime /* mariadb-5.3 */ | NO   | PRI | NULL    |                |
| campaignid                          | mediumint(8) unsigned      | NO   | MUL | NULL    |                |
| c_type                              | smallint(5) unsigned       | NO   |     | NULL    |                |
| d_type                              | varchar(16)                | YES  |     | NULL    |                |
| clientid                            | mediumint(8) unsigned      | YES  | MUL | NULL    |                |
| bids                                | int(10) unsigned           | NO   |     | 0       |                |
| requests                            | int(10) unsigned           | NO   |     | 0       |                |
| updated                             | datetime /* mariadb-5.3 */ | YES  |     | NULL    |                |
+-------------------------------------+----------------------------+------+-----+---------+----------------+
9 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:55:57>DESCRIBE OPENX_V1_STATS.ox_data_summary_creative_hourly;
+-------------+----------------------------+------+-----+---------------------+-------+
| Field       | Type                       | Null | Key | Default             | Extra |
+-------------+----------------------------+------+-----+---------------------+-------+
| date_time   | datetime /* mariadb-5.3 */ | NO   | PRI | NULL                |       |
| campaignid  | int(10) unsigned           | NO   | PRI | NULL                |       |
| creativeid  | int(10) unsigned           | NO   | PRI | NULL                |       |
| zone_id     | int(10) unsigned           | NO   | PRI | NULL                |       |
| requests    | int(10) unsigned           | NO   |     | 0                   |       |
| impressions | int(10) unsigned           | NO   |     | 0                   |       |
| clicks      | int(10) unsigned           | NO   |     | 0                   |       |
| updated     | datetime /* mariadb-5.3 */ | NO   |     | current_timestamp() |       |
+-------------+----------------------------+------+-----+---------------------+-------+
8 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:56:00>DESCRIBE OPENX_V1_STATS.ox_tg_campaign_bidding;
+-----------------+----------------------------+------+-----+---------+-------+
| Field           | Type                       | Null | Key | Default | Extra |
+-----------------+----------------------------+------+-----+---------+-------+
| date_time       | datetime /* mariadb-5.3 */ | NO   | PRI | NULL    |       |
| campaign_id     | int(11)                    | NO   | PRI | NULL    |       |
| bidding_revenue | decimal(23,8)              | NO   | PRI | NULL    |       |
| bidding_cnt     | int(11)                    | YES  |     | NULL    |       |
+-----------------+----------------------------+------+-----+---------+-------+
4 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:56:03>DESCRIBE OPENX_V1_STATS.ox_data_summary_rtb_daily_ad;
+------------------------------+----------------------------+------+-----+---------+----------------+
| Field                        | Type                       | Null | Key | Default | Extra          |
+------------------------------+----------------------------+------+-----+---------+----------------+
| data_summary_rtb_daily_ad_id | bigint(20) unsigned        | NO   | PRI | NULL    | auto_increment |
| date_time                    | datetime /* mariadb-5.3 */ | NO   | PRI | NULL    |                |
| ad_id                        | int(10) unsigned           | NO   | MUL | NULL    |                |
| campaignid                   | mediumint(8) unsigned      | NO   |     | NULL    |                |
| c_type                       | smallint(5) unsigned       | NO   |     | NULL    |                |
| d_type                       | varchar(16)                | YES  |     | NULL    |                |
| clientid                     | mediumint(8) unsigned      | YES  | MUL | NULL    |                |
| bids                         | int(10) unsigned           | NO   |     | 0       |                |
| requests                     | int(10) unsigned           | NO   |     | 0       |                |
| updated                      | datetime /* mariadb-5.3 */ | YES  |     | NULL    |                |
+------------------------------+----------------------------+------+-----+---------+----------------+
10 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:56:07>DESCRIBE OPENX_V1_STATS.ox_wp_data_raw_xc_item;
+--------------------+----------------------------+------+-----+------------+----------------+
| Field              | Type                       | Null | Key | Default    | Extra          |
+--------------------+----------------------------+------+-----+------------+----------------+
| conversion_item_id | bigint(20) unsigned        | NO   | PRI | NULL       | auto_increment |
| server_ip          | varchar(40)                | NO   | PRI |            |                |
| date_time          | datetime /* mariadb-5.3 */ | NO   | MUL | NULL       |                |
| action_date_time   | datetime /* mariadb-5.3 */ | NO   |     | NULL       |                |
| creative_id        | mediumint(9) unsigned      | NO   | MUL | NULL       |                |
| zone_id            | mediumint(9) unsigned      | NO   | MUL | NULL       |                |
| ip_address         | varchar(40)                | NO   |     | NULL       |                |
| map_id             | text                       | YES  |     | NULL       |                |
| basket_value       | decimal(23,8)              | NO   |     | 0.00000000 |                |
| num_items          | int(10) unsigned           | NO   |     | 1          |                |
| oaid               | varchar(50)                | YES  |     | NULL       |                |
| title              | text                       | YES  |     | NULL       |                |
| order_code         | varchar(256)               | YES  |     | NULL       |                |
| inside_window      | tinyint(1)                 | YES  |     | 0          |                |
| currency_id        | mediumint(9) unsigned      | NO   |     | 1          |                |
| event_type         | varchar(20)                | YES  |     | NULL       |                |
| conversion_id      | bigint(20) unsigned        | YES  |     | NULL       |                |
+--------------------+----------------------------+------+-----+------------+----------------+
17 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:56:10>DESCRIBE OPENX_V1_STATS.campaign_report_daily_vw;
+-----------------------------+----------------------------+------+-----+---------+-------+
| Field                       | Type                       | Null | Key | Default | Extra |
+-----------------------------+----------------------------+------+-----+---------+-------+
| date_time                   | datetime /* mariadb-5.3 */ | YES  |     | NULL    |       |
| client_id                   | mediumint(9)               | YES  |     | NULL    |       |
| campaign_id                 | mediumint(9) unsigned      | NO   |     | 0       |       |
| campaign_name               | varchar(255)               | YES  |     | NULL    |       |
| daily_ad_target_budget      | decimal(16,0)              | YES  |     | NULL    |       |
| impressions                 | decimal(32,0)              | YES  |     | NULL    |       |
| clicks                      | decimal(32,0)              | YES  |     | NULL    |       |
| CTR                         | decimal(38,2)              | NO   |     | 0.00    |       |
| conversions                 | decimal(32,0)              | YES  |     | NULL    |       |
| CVR                         | decimal(38,2)              | NO   |     | 0.00    |       |
| conversion_revenue          | decimal(38,0)              | YES  |     | NULL    |       |
| conversion_items            | decimal(32,0)              | YES  |     | NULL    |       |
| conversions_oneday          | decimal(32,0)              | YES  |     | NULL    |       |
| conversion_revenue_oneday   | decimal(38,0)              | YES  |     | NULL    |       |
| conversion_items_oneday     | decimal(32,0)              | YES  |     | NULL    |       |
| ad_cost                     | decimal(44,0)              | YES  |     | NULL    |       |
| ad_cost_target_budget_ratio | decimal(52,2)              | NO   |     | 0.00    |       |
| CPC                         | decimal(44,0)              | NO   |     | 0       |       |
| CPM                         | decimal(47,0)              | NO   |     | 0       |       |
| media_cost                  | decimal(44,0)              | YES  |     | NULL    |       |
| media_cost_ratio            | decimal(53,3)              | NO   |     | 0.000   |       |
| ROAS                        | decimal(53,0)              | NO   |     | 0       |       |
| ROAS_oneday                 | decimal(53,0)              | NO   |     | 0       |       |
+-----------------------------+----------------------------+------+-----+---------+-------+
23 rows in set (0.003 sec)

root@localhost:OPENX_V1_STATS 17:56:13>DESCRIBE OPENX_V1_STATS.ox_data_all_creatives;
+-------------+---------------------+------+-----+---------+-------+
| Field       | Type                | Null | Key | Default | Extra |
+-------------+---------------------+------+-----+---------+-------+
| bannerid    | mediumint(9)        | NO   | PRI | NULL    |       |
| creativeid  | int(11)             | NO   | PRI | NULL    |       |
| zoneid      | int(11)             | NO   |     | NULL    |       |
| impressions | bigint(20) unsigned | NO   |     | 0       |       |
| clicks      | bigint(20) unsigned | NO   |     | 0       |       |
+-------------+---------------------+------+-----+---------+-------+
5 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:56:17>DESCRIBE OPENX_V1_STATS.campaign_report_hourly_vw;
+------------------------------+----------------------------+------+-----+---------+-------+
| Field                        | Type                       | Null | Key | Default | Extra |
+------------------------------+----------------------------+------+-----+---------+-------+
| date_hour                    | datetime /* mariadb-5.3 */ | NO   |     | NULL    |       |
| clientid                     | mediumint(9)               | YES  |     | 0       |       |
| campaignid                   | mediumint(9) unsigned      | NO   |     | NULL    |       |
| campaignname                 | varchar(255)               | YES  |     |         |       |
| campaign_target_budget_daily | decimal(16,0)              | YES  |     | NULL    |       |
| impressions                  | decimal(32,0)              | YES  |     | NULL    |       |
| clicks                       | decimal(32,0)              | YES  |     | NULL    |       |
| CTR                          | decimal(38,2)              | NO   |     | 0.00    |       |
| conversions                  | decimal(32,0)              | YES  |     | NULL    |       |
| CVR                          | decimal(38,2)              | NO   |     | 0.00    |       |
| conversion_revenue           | decimal(38,0)              | YES  |     | NULL    |       |
| conversion_items             | decimal(32,0)              | YES  |     | NULL    |       |
| conversions_oneday           | decimal(32,0)              | YES  |     | NULL    |       |
| conversion_revenue_oneday    | decimal(38,0)              | YES  |     | NULL    |       |
| conversion_items_oneday      | decimal(32,0)              | YES  |     | NULL    |       |
| ad_cost                      | decimal(44,0)              | YES  |     | NULL    |       |
| CPC                          | decimal(44,0)              | NO   |     | 0       |       |
| CPM                          | decimal(47,0)              | NO   |     | 0       |       |
| media_cost                   | decimal(44,0)              | YES  |     | NULL    |       |
| media_cost_ratio             | decimal(53,3)              | NO   |     | 0.000   |       |
| ROAS                         | decimal(53,0)              | NO   |     | 0       |       |
| ROAS_oneday                  | decimal(53,0)              | NO   |     | 0       |       |
| conversion_ad_cost_ratio     | decimal(40,2)              | NO   |     | 0.00    |       |
+------------------------------+----------------------------+------+-----+---------+-------+
23 rows in set (0.002 sec)

root@localhost:OPENX_V1_STATS 17:56:22>DESCRIBE OPENX_V1_STATS.ox_time_dimension;
+--------------+----------------------------+------+-----+---------+-------+
| Field        | Type                       | Null | Key | Default | Extra |
+--------------+----------------------------+------+-----+---------+-------+
| id           | char(10)                   | NO   | PRI | NULL    |       |
| db_datetime  | datetime /* mariadb-5.3 */ | NO   | MUL | NULL    |       |
| db_date      | date                       | NO   |     | NULL    |       |
| quarter      | char(1)                    | NO   |     | NULL    |       |
| week         | char(2)                    | NO   |     | NULL    |       |
| day_name     | char(9)                    | NO   |     | NULL    |       |
| month_name   | char(9)                    | NO   |     | NULL    |       |
| holiday_flag | char(1)                    | YES  |     | f       |       |
| weekend_flag | char(1)                    | YES  |     | f       |       |
| event        | varchar(50)                | YES  |     | NULL    |       |
+--------------+----------------------------+------+-----+---------+-------+
10 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:56:25>DESCRIBE OPENX_V1_STATS.ox_wp_data_raw_pc_item;
+--------------------+----------------------------+------+-----+------------+----------------+
| Field              | Type                       | Null | Key | Default    | Extra          |
+--------------------+----------------------------+------+-----+------------+----------------+
| conversion_item_id | bigint(20) unsigned        | NO   | PRI | NULL       | auto_increment |
| server_ip          | varchar(40)                | NO   | PRI |            |                |
| date_time          | datetime /* mariadb-5.3 */ | NO   | PRI | NULL       |                |
| action_date_time   | datetime /* mariadb-5.3 */ | NO   |     | NULL       |                |
| creative_id        | mediumint(9) unsigned      | NO   | MUL | NULL       |                |
| zone_id            | mediumint(9) unsigned      | NO   | MUL | NULL       |                |
| ip_address         | varchar(40)                | NO   |     | NULL       |                |
| map_id             | text                       | YES  |     | NULL       |                |
| basket_value       | decimal(23,8)              | NO   |     | 0.00000000 |                |
| num_items          | int(10) unsigned           | NO   |     | 1          |                |
| oaid               | varchar(50)                | YES  |     | NULL       |                |
| title              | text                       | YES  |     | NULL       |                |
| order_code         | varchar(256)               | YES  |     | NULL       |                |
| inside_window      | tinyint(1)                 | YES  |     | 0          |                |
| currency_id        | mediumint(9) unsigned      | NO   |     | 1          |                |
| event_type         | varchar(20)                | YES  |     | NULL       |                |
| conversion_id      | bigint(20) unsigned        | YES  |     | NULL       |                |
+--------------------+----------------------------+------+-----+------------+----------------+
17 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:56:31>DESCRIBE OPENX_V1_STATS.etl_feed_ox_data_summary_ad_hourly;
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| Field                                       | Type                       | Null | Key | Default    | Extra          |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
| data_summary_ad_hourly_id                   | bigint(20) unsigned        | NO   | PRI | NULL       | auto_increment |
| date_time                                   | datetime /* mariadb-5.3 */ | NO   | PRI | NULL       |                |
| ad_id                                       | int(10) unsigned           | NO   | MUL | NULL       |                |
| creative_id                                 | int(10) unsigned           | NO   |     | NULL       |                |
| zone_id                                     | int(10) unsigned           | NO   | MUL | NULL       |                |
| bids                                        | int(10) unsigned           | YES  |     | 0          |                |
| wins                                        | int(10) unsigned           | YES  |     | 0          |                |
| requests                                    | int(10) unsigned           | NO   |     | 0          |                |
| impressions                                 | int(10) unsigned           | NO   |     | 0          |                |
| clicks                                      | int(10) unsigned           | NO   |     | 0          |                |
| conversions                                 | int(10) unsigned           | NO   |     | 0          |                |
| total_basket_value                          | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_num_items                             | int(11)                    | YES  |     | 0          |                |
| total_revenue                               | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_cost                                  | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| total_techcost                              | decimal(10,4)              | YES  |     | 0.0000     |                |
| updated                                     | datetime /* mariadb-5.3 */ | NO   |     | NULL       |                |
| assisted_conversions                        | int(10)                    | NO   |     | 0          |                |
| total_assisted_basket_value                 | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_assisted_num_items                    | int(10)                    | NO   |     | 0          |                |
| view_through_conversions                    | int(10)                    | NO   |     | 0          |                |
| total_view_through_basket_value             | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_view_through_num_items                | int(10)                    | NO   |     | 0          |                |
| total_rscpm                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| oneday_conversions                          | int(10)                    | NO   |     | 0          |                |
| total_oneday_basket_value                   | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_oneday_num_items                      | int(10)                    | YES  |     | 0          |                |
| total_gross                                 | decimal(23,8) unsigned     | YES  |     | 0.00000000 |                |
| abuse_click                                 | int(10) unsigned           | NO   |     | 0          |                |
| over_click                                  | int(10) unsigned           | NO   |     | 0          |                |
| currency_id                                 | mediumint(9) unsigned      | NO   |     | 1          |                |
| new_user_click                              | int(10) unsigned           | YES  |     | 0          |                |
| campaignid                                  | mediumint(9) unsigned      | YES  |     | 0          |                |
| d_type                                      | varchar(16)                | YES  |     | NULL       |                |
| c_type                                      | smallint(6) unsigned       | YES  |     | 0          |                |
| clientid                                    | mediumint(9) unsigned      | YES  |     | 0          |                |
| affiliateid                                 | mediumint(9) unsigned      | YES  |     | 0          |                |
| dmp_code                                    | int(10) unsigned           | YES  |     | 0          |                |
| dmp_sales_code                              | int(10) unsigned           | YES  |     | 0          |                |
| total_dmp                                   | decimal(23,8)              | YES  |     | 0.00000000 |                |
| play_impressions                            | int(10) unsigned           | YES  |     | 0          |                |
| avg_play_time                               | bigint(20) unsigned        | YES  |     | 0          |                |
| default_conversions                         | int(10) unsigned           | YES  |     | 0          |                |
| total_default_conversions_basket_value      | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_default_conversions_num_items         | int(10) unsigned           | YES  |     | 0          |                |
| cross_conversions                           | int(10) unsigned           | YES  |     | 0          |                |
| total_cross_conversions_basket_value        | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_cross_conversions_num_items           | int(10) unsigned           | YES  |     | 0          |                |
| plays                                       | int(10) unsigned           | NO   |     | 0          |                |
| abuse_play                                  | int(10) unsigned           | NO   |     | 0          |                |
| over_play                                   | int(10) unsigned           | NO   |     | 0          |                |
| new_user_play                               | int(10) unsigned           | NO   |     | 0          |                |
| play_conversions                            | int(10) unsigned           | NO   |     | 0          |                |
| total_play_conversions_basket_value         | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_play_conversions_num_items            | int(10) unsigned           | YES  |     | 0          |                |
| oneday_play_conversions                     | int(10) unsigned           | YES  |     | 0          |                |
| total_oneday_play_conversions_basket_value  | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_oneday_play_conversions_num_items     | int(10) unsigned           | YES  |     | 0          |                |
| default_play_conversions                    | int(10) unsigned           | YES  |     | 0          |                |
| total_default_play_conversions_basket_value | decimal(23,8)              | YES  |     | 0.00000000 |                |
| total_default_play_conversions_num_items    | int(10) unsigned           | YES  |     | 0          |                |
+---------------------------------------------+----------------------------+------+-----+------------+----------------+
61 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:56:36> DESCRIBE OPENX_V1_STATS.rta_active_campaign;
+--------------+----------------------------+------+-----+---------------------+----------------+
| Field        | Type                       | Null | Key | Default             | Extra          |
+--------------+----------------------------+------+-----+---------------------+----------------+
| id           | mediumint(9)               | NO   | PRI | NULL                | auto_increment |
| campaignid   | mediumint(9)               | NO   |     | 0                   |                |
| campaignname | varchar(255)               | NO   |     |                     |                |
| date_time    | datetime /* mariadb-5.3 */ | NO   |     | current_timestamp() |                |
+--------------+----------------------------+------+-----+---------------------+----------------+
4 rows in set (0.001 sec)

root@localhost:OPENX_V1_STATS 17:56:40>DESCRIBE OPENX_V1_STATS.ox_client_remain_budget_daily;
+---------------+-----------------------------+------+-----+---------------------+-------+
| Field         | Type                        | Null | Key | Default             | Extra |
+---------------+-----------------------------+------+-----+---------------------+-------+
| date_time     | datetime /* mariadb-5.3 */  | NO   | PRI | NULL                |       |
| clientid      | mediumint(9)                | NO   | PRI | NULL                |       |
| remain_budget | decimal(23,8)               | NO   |     | NULL                |       |
| updated       | timestamp /* mariadb-5.3 */ | NO   |     | current_timestamp() |       |
+---------------+-----------------------------+------+-----+---------------------+-------+
4 rows in set (0.001 sec)