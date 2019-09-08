# structuredpriorsmrp_public

Arxiv preprint: https://arxiv.org/abs/1908.06716

## Steps to run simulation pipeline in simulation directory
1. The two .dta files in poststrat_pipeline_testing_age3_v3_posteriorvariance.R are retrieved from the paper, Estimating State Public Opinion with Multi-level Regression and Poststratification using R. URL: https://scholar.princeton.edu/jkastellec/publications. Download these two files before running the simulation pipeline, and put them in the simulation directory.
2. Choose age preference curve with coef_age in poststrat_pipeline_testing_age3_v3_posteriorvariance.R
3. Choose sample size, simulation runs, probability indices and number of age categories with sample_size, runs, r, age_grouping_multiplier in poststrat_pipeline_testing_age3_v3_posteriorvariance.R
4. Run poststrat_pipeline_testing_age3_v3_posteriorvariance.R
5. Run threemodelwriteup_v3_posteriorvariance.R with the same configurations. This will produce the bias plots shown in the paper for a given configuration.


## Steps to run data analysis on 2008 Annenberg phone survey in realdata_annenberg directory
1. Request access for the 2008 National Annenberg Election Survey (NAES) telephone from the Annenberg Public Policy Center and put the phone survey text file into the realdata_annenberg directory. Rename it to annenbergphone2008.txt
2. acs_ps.rds is the 5-year American Community Survey (ACS) in a cleaned-up format. Create a new path ~/Desktop/annenbergdata/fiveyearacs/ and then download the 5-year ACS and unzip in this path. Finally, run ACS_PS_annenberg_fiveyear.R in the preprocess directory to get acs_ps.rds in ~/Desktop/annenbergdata/fiveyearacs/
3. Make sure state_level_update.dta, gay_marriage_megapoll.dta, acs_ps.rds, annenbergphone2008.txt are in realdata_annenberg directory. The first two files are from Step 1 in the simulation pipeline.
4. Run fitmodel_annenberg_v3.R for age_grouping_multiplier = 12,48,72 and for all three models in the variables m_file,m_name
5. Run poststrat_annenberg_v3.R