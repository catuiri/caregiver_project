ADA final project
================
Clifford Atuiri
2022-12-08

``` r
##loading package##
pacman::p_load(haven)
```

``` r
## importing dataset
caregiver<-read_dta("hints5_combined1234.dta")
```

``` r
#selecting variables of interest 
colnames(caregiver)
```

    ##    [1] "hhid"                             "personid"                        
    ##    [3] "stratum"                          "app_region"                      
    ##    [5] "highspanli"                       "hispsurname"                     
    ##    [7] "hisp_hh"                          "ruc2003"                         
    ##    [9] "ruc2013"                          "pr_ruca_2010"                    
    ##   [11] "sec_ruca_2010"                    "sec_ruca_2010_descript"          
    ##   [13] "nchsurcode2013"                   "censdiv"                         
    ##   [15] "censreg"                          "formtype"                        
    ##   [17] "language_flag"                    "qdisp"                           
    ##   [19] "updatedate"                       "adultsinhh"                      
    ##   [21] "mailhhadults"                     "seekhealthinfo"                  
    ##   [23] "whereseekhealthinfo"              "wholookingfor"                   
    ##   [25] "lotofeffort"                      "frustrated"                      
    ##   [27] "concernedquality"                 "toohardunderstand"               
    ##   [29] "confidentgethealthinf"            "trustdoctor"                     
    ##   [31] "trustfamily"                      "trustnewsmag"                    
    ##   [33] "trustradio"                       "trustinternet"                   
    ##   [35] "trusttelevision"                  "trustgov"                        
    ##   [37] "trustcharities"                   "trustreligiousorgs"              
    ##   [39] "strongneedhealthinfo"             "strongneedhealthinfo_os"         
    ##   [41] "seekcancerinfo"                   "internetcancerinfoself"          
    ##   [43] "useinternet"                      "internet_dialup"                 
    ##   [45] "internet_broadbnd"                "internet_cell"                   
    ##   [47] "internet_wifi"                    "whereuseinternet_home"           
    ##   [49] "whereuseinternet_work"            "whereuseinternet_school"         
    ##   [51] "whereuseinternet_publicplace"     "whereuseinternet_mobiledevice"   
    ##   [53] "whereuseinternet_gamingdevice"    "electronic_selfhealthinfo"       
    ##   [55] "electronic_healthinfose"          "electronic_buymedicine"          
    ##   [57] "electronic_hcpsearch"             "electronic_talkdoctor"           
    ##   [59] "electronic_madeappts"             "electronic_trackedhealthcosts"   
    ##   [61] "electronic_completedforms"        "electronic_testresults"          
    ##   [63] "havedevice_tablet"                "havedevice_smartph"              
    ##   [65] "havedevice_cellph"                "tablethealthwellnessapps"        
    ##   [67] "tablet_achievegoal"               "tablet_makedecision"             
    ##   [69] "tablet_discussionshcp"            "otherdevtrackhealth"             
    ##   [71] "sharedhealthdeviceinfo"           "intrsn_visitedsocnet"            
    ##   [73] "intrsn_sharedsocnet"              "intrsn_wroteblog"                
    ##   [75] "intrsn_supportgroup"              "intrsn_youtube"                  
    ##   [77] "textfromdoctor"                   "regularprovider"                 
    ##   [79] "mostrecentcheckup2"               "freqgoprovider"                  
    ##   [81] "chanceaskquestions"               "feelingsaddressed"               
    ##   [83] "involveddecisions"                "understoodnextsteps"             
    ##   [85] "explainedclearly"                 "spentenoughtime"                 
    ##   [87] "helpuncertainty"                  "qualitycare"                     
    ##   [89] "probcare_bringtest"               "probcare_waitlong"               
    ##   [91] "probcare_redotest"                "probcare_providehist"            
    ##   [93] "healthins_insuranceemp"           "healthins_insurancepriv"         
    ##   [95] "healthins_medicare"               "healthins_medicaid"              
    ##   [97] "healthins_tricare"                "healthins_va"                    
    ##   [99] "healthins_ihs"                    "healthins_other"                 
    ##  [101] "healthins_other_os"               "healthinsurance"                 
    ##  [103] "providermaintainemr2"             "offeredaccesshcp2"               
    ##  [105] "offeredaccessinsurer2"            "hcpencourageonlinerec"           
    ##  [107] "accessonlinerecord"               "notaccessed_speakdirectly"       
    ##  [109] "notaccessed_nointernet"           "notaccessed_noneed"              
    ##  [111] "notaccessed_concernedprivacy"     "notaccessed_norecord"            
    ##  [113] "notaccessed_other"                "notaccessed_other_os"            
    ##  [115] "recordsonline_labs"               "recordsonline_meds"              
    ##  [117] "recordsonline_healthprobs"        "recordsonline_allergies"         
    ##  [119] "recordsonline_visitsummary"       "recordsonline_clinnotes"         
    ##  [121] "recordsonline_immunizations"      "recordsonline_makeappt"          
    ##  [123] "recordsonline_refillmeds"         "recordsonline_paperwork"         
    ##  [125] "recordsonline_requestcorrection"  "recordsonline_messagehcp"        
    ##  [127] "recordsonline_viewresults"        "recordsonline_monitorhealth"     
    ##  [129] "recordsonline_downloadhealth"     "recordsonline_addhealthinfo"     
    ##  [131] "recordsonline_makedecision"       "esent_anotherhcp"                
    ##  [133] "esent_family"                     "esent_healthapp"                 
    ##  [135] "understandonlinemedrec"           "usefulonlinemedrec"              
    ##  [137] "confidentinfosafe"                "withheldinfoprivacy"             
    ##  [139] "electinfosafe"                    "accessfamilymedrec"              
    ##  [141] "accessedfamrec_theirpwd"          "accessedfamrec_mypwd"            
    ##  [143] "caregiving_child"                 "caregiving_spouse"               
    ##  [145] "caregiving_parent"                "caregiving_family"               
    ##  [147] "caregiving_friend"                "caregiving_no"                   
    ##  [149] "caregivingwho_cat"                "caregiving_cancer"               
    ##  [151] "caregiving_alzheimers"            "caregiving_orthomusc"            
    ##  [153] "caregiving_mentalhealth"          "caregiving_chroniccond"          
    ##  [155] "caregiving_neurodev"              "caregiving_acutecond"            
    ##  [157] "caregiving_aging"                 "caregiving_notsure"              
    ##  [159] "caregiving_other"                 "caregiving_other_os"             
    ##  [161] "caregivingcond_cat"               "caregiving_hoursperweek"         
    ##  [163] "hearddnatest"                     "genetictestuse_determinerisk"    
    ##  [165] "genetictestuse_determinetx"       "genetictestuse_determinemed"     
    ##  [167] "genetictestuse_determinepass"     "genetictestuse_cat"              
    ##  [169] "hadtest_paternity"                "hadtest_ancestry"                
    ##  [171] "hadtest_dnafing"                  "hadtest_cfcarrier"               
    ##  [173] "hadtest_brca"                     "hadtest_lynch"                   
    ##  [175] "hadtest_none"                     "hadtest_notsure"                 
    ##  [177] "hadtest_other"                    "hadtest_other_os"                
    ##  [179] "hadtest_cat"                      "generalhealth"                   
    ##  [181] "ownabilitytakecarehealth"         "medconditions_diabetes"          
    ##  [183] "medconditions_highbp"             "medconditions_heartcondition"    
    ##  [185] "medconditions_lungdisease"        "medconditions_arthritis"         
    ##  [187] "medconditions_depression"         "height_feet"                     
    ##  [189] "height_inches"                    "weight"                          
    ##  [191] "littleinterest"                   "hopeless"                        
    ##  [193] "nervous"                          "worrying"                        
    ##  [195] "emotionalsupport"                 "talkhealthfriends"               
    ##  [197] "helpdailychores"                  "deaf"                            
    ##  [199] "usemenucalorieinfo"               "fruit"                           
    ##  [201] "vegetables"                       "alcoholconditions_cancer"        
    ##  [203] "alcoholconditions_heartdisease"   "alcoholconditions_diabetes"      
    ##  [205] "alcoholconditions_cholesterol"    "alcoholconditions_liverdisease"  
    ##  [207] "alcoholconditions_overweight"     "alcoholincreasecancer"           
    ##  [209] "alcoholreduceheart"               "timesmoderateexercise"           
    ##  [211] "howlongmoderateexercisemn"        "howlongmoderateexercisehr"       
    ##  [213] "timesstrengthtraining"            "tanningbed"                      
    ##  [215] "skincancerhpexam"                 "skincancerselfcheck"             
    ##  [217] "smoke100"                         "smokenow"                        
    ##  [219] "triedquit"                        "considerquit"                    
    ##  [221] "electciglessharm"                 "usedecigever"                    
    ##  [223] "useecignow"                       "drtalklungtest"                  
    ##  [225] "smokelesslessharm"                "hookahlessharm"                  
    ##  [227] "genderc"                          "whenpaptest"                     
    ##  [229] "whenmammogram"                    "everhadpsatest"                  
    ##  [231] "heardhpv"                         "hpvcausecancer_cervical"         
    ##  [233] "hpvcausecancer_penile"            "hpvcausecancer_anal"             
    ##  [235] "hpvcausecancer_oral"              "hpvstd"                          
    ##  [237] "hpvmedicaltreatment"              "heardhpvvaccine2"                
    ##  [239] "hpvshotprevent"                   "fambetween9and27"                
    ##  [241] "discusshpvvaccination12m"         "recommendhpvshot"                
    ##  [243] "everhadcancer"                    "cabladder"                       
    ##  [245] "cabone"                           "cabreast"                        
    ##  [247] "cacervical"                       "cacolon"                         
    ##  [249] "caendometrial"                    "caheadneck"                      
    ##  [251] "cahodgkins"                       "caleukemia"                      
    ##  [253] "caliver"                          "calung"                          
    ##  [255] "camelanoma"                       "canonhodgkin"                    
    ##  [257] "caoral"                           "caovarian"                       
    ##  [259] "capancreatic"                     "capharyngeal"                    
    ##  [261] "caprostate"                       "carectal"                        
    ##  [263] "carenal"                          "caskin"                          
    ##  [265] "castomach"                        "caother"                         
    ##  [267] "caother_os"                       "cancer_cat"                      
    ##  [269] "whendiagnosedcancer"              "undergocancertreatment"          
    ##  [271] "cancertx_chemo"                   "cancertx_radiation"              
    ##  [273] "cancertx_surgery"                 "cancertx_other"                  
    ##  [275] "howlongfinishtreatment_cat"       "cancertxsummary"                 
    ##  [277] "cancerdeniedcoverage"             "cancerhurtfinances"              
    ##  [279] "cancerabilitytowork"              "clinicaltrialcancertx"           
    ##  [281] "discussedclinicaltrial"           "chancegetcancer"                 
    ##  [283] "everythingcausecancer"            "preventnotpossible"              
    ##  [285] "toomanyrecommendations"           "cancermorecommon"                
    ##  [287] "cancerfatal"                      "rathernotknowchance"             
    ##  [289] "freqworrycancer"                  "familyeverhadcancer"             
    ##  [291] "age"                              "occupationstatus"                
    ##  [293] "occupationstatus_os"              "employed"                        
    ##  [295] "unemployed"                       "homemaker"                       
    ##  [297] "student"                          "retired"                         
    ##  [299] "disabled"                         "otherocc"                        
    ##  [301] "multiocc"                         "activedutyarmedforces"           
    ##  [303] "receivedcareva"                   "maritalstatus"                   
    ##  [305] "education"                        "borninusa"                       
    ##  [307] "yearcametousa"                    "speakenglish"                    
    ##  [309] "nothisp"                          "mexican"                         
    ##  [311] "puertorican"                      "cuban"                           
    ##  [313] "othhisp"                          "hisp_cat"                        
    ##  [315] "white"                            "black"                           
    ##  [317] "amerind"                          "asind"                           
    ##  [319] "chinese"                          "filipino"                        
    ##  [321] "japanese"                         "korean"                          
    ##  [323] "vietnamese"                       "othasian"                        
    ##  [325] "hawaiian"                         "guamanian"                       
    ##  [327] "samoan"                           "othpacisl"                       
    ##  [329] "race_cat2"                        "sexualorientation"               
    ##  [331] "sexualorientation_os"             "totalhousehold"                  
    ##  [333] "r_hhadults"                       "hhadults_num"                    
    ##  [335] "selfgender"                       "selfage"                         
    ##  [337] "selfmob"                          "hhadultgender2"                  
    ##  [339] "hhadultage2"                      "hhadultmob2"                     
    ##  [341] "hhadultgender3"                   "hhadultage3"                     
    ##  [343] "hhadultmob3"                      "hhadultgender4"                  
    ##  [345] "hhadultage4"                      "hhadultmob4"                     
    ##  [347] "hhadultgender5"                   "hhadultage5"                     
    ##  [349] "hhadultmob5"                      "childreninhh"                    
    ##  [351] "rentorown"                        "cellphone"                       
    ##  [353] "phoneinhome"                      "incomeranges"                    
    ##  [355] "mailsurveytime_min"               "mailsurveytime_hrs"              
    ##  [357] "typeofaddressa"                   "typeofaddressb"                  
    ##  [359] "typeofaddressc"                   "typeofaddressd"                  
    ##  [361] "person_finwt0"                    "person_finwt1"                   
    ##  [363] "person_finwt2"                    "person_finwt3"                   
    ##  [365] "person_finwt4"                    "person_finwt5"                   
    ##  [367] "person_finwt6"                    "person_finwt7"                   
    ##  [369] "person_finwt8"                    "person_finwt9"                   
    ##  [371] "person_finwt10"                   "person_finwt11"                  
    ##  [373] "person_finwt12"                   "person_finwt13"                  
    ##  [375] "person_finwt14"                   "person_finwt15"                  
    ##  [377] "person_finwt16"                   "person_finwt17"                  
    ##  [379] "person_finwt18"                   "person_finwt19"                  
    ##  [381] "person_finwt20"                   "person_finwt21"                  
    ##  [383] "person_finwt22"                   "person_finwt23"                  
    ##  [385] "person_finwt24"                   "person_finwt25"                  
    ##  [387] "person_finwt26"                   "person_finwt27"                  
    ##  [389] "person_finwt28"                   "person_finwt29"                  
    ##  [391] "person_finwt30"                   "person_finwt31"                  
    ##  [393] "person_finwt32"                   "person_finwt33"                  
    ##  [395] "person_finwt34"                   "person_finwt35"                  
    ##  [397] "person_finwt36"                   "person_finwt37"                  
    ##  [399] "person_finwt38"                   "person_finwt39"                  
    ##  [401] "person_finwt40"                   "person_finwt41"                  
    ##  [403] "person_finwt42"                   "person_finwt43"                  
    ##  [405] "person_finwt44"                   "person_finwt45"                  
    ##  [407] "person_finwt46"                   "person_finwt47"                  
    ##  [409] "person_finwt48"                   "person_finwt49"                  
    ##  [411] "person_finwt50"                   "var_stratum"                     
    ##  [413] "var_cluster"                      "agegrpa"                         
    ##  [415] "agegrpb"                          "educa"                           
    ##  [417] "educb"                            "raceethn"                        
    ##  [419] "raceethn5"                        "hhinc"                           
    ##  [421] "bmi"                              "agedx"                           
    ##  [423] "timesincedx"                      "smokestat"                       
    ##  [425] "phq4"                             "weeklyminutesmoderateexercise"   
    ##  [427] "eciguse"                          "incomeranges_imp"                
    ##  [429] "nwgt0"                            "nwgt1"                           
    ##  [431] "nwgt51"                           "nwgt101"                         
    ##  [433] "nwgt151"                          "nwgt2"                           
    ##  [435] "nwgt52"                           "nwgt102"                         
    ##  [437] "nwgt152"                          "nwgt3"                           
    ##  [439] "nwgt53"                           "nwgt103"                         
    ##  [441] "nwgt153"                          "nwgt4"                           
    ##  [443] "nwgt54"                           "nwgt104"                         
    ##  [445] "nwgt154"                          "nwgt5"                           
    ##  [447] "nwgt55"                           "nwgt105"                         
    ##  [449] "nwgt155"                          "nwgt6"                           
    ##  [451] "nwgt56"                           "nwgt106"                         
    ##  [453] "nwgt156"                          "nwgt7"                           
    ##  [455] "nwgt57"                           "nwgt107"                         
    ##  [457] "nwgt157"                          "nwgt8"                           
    ##  [459] "nwgt58"                           "nwgt108"                         
    ##  [461] "nwgt158"                          "nwgt9"                           
    ##  [463] "nwgt59"                           "nwgt109"                         
    ##  [465] "nwgt159"                          "nwgt10"                          
    ##  [467] "nwgt60"                           "nwgt110"                         
    ##  [469] "nwgt160"                          "nwgt11"                          
    ##  [471] "nwgt61"                           "nwgt111"                         
    ##  [473] "nwgt161"                          "nwgt12"                          
    ##  [475] "nwgt62"                           "nwgt112"                         
    ##  [477] "nwgt162"                          "nwgt13"                          
    ##  [479] "nwgt63"                           "nwgt113"                         
    ##  [481] "nwgt163"                          "nwgt14"                          
    ##  [483] "nwgt64"                           "nwgt114"                         
    ##  [485] "nwgt164"                          "nwgt15"                          
    ##  [487] "nwgt65"                           "nwgt115"                         
    ##  [489] "nwgt165"                          "nwgt16"                          
    ##  [491] "nwgt66"                           "nwgt116"                         
    ##  [493] "nwgt166"                          "nwgt17"                          
    ##  [495] "nwgt67"                           "nwgt117"                         
    ##  [497] "nwgt167"                          "nwgt18"                          
    ##  [499] "nwgt68"                           "nwgt118"                         
    ##  [501] "nwgt168"                          "nwgt19"                          
    ##  [503] "nwgt69"                           "nwgt119"                         
    ##  [505] "nwgt169"                          "nwgt20"                          
    ##  [507] "nwgt70"                           "nwgt120"                         
    ##  [509] "nwgt170"                          "nwgt21"                          
    ##  [511] "nwgt71"                           "nwgt121"                         
    ##  [513] "nwgt171"                          "nwgt22"                          
    ##  [515] "nwgt72"                           "nwgt122"                         
    ##  [517] "nwgt172"                          "nwgt23"                          
    ##  [519] "nwgt73"                           "nwgt123"                         
    ##  [521] "nwgt173"                          "nwgt24"                          
    ##  [523] "nwgt74"                           "nwgt124"                         
    ##  [525] "nwgt174"                          "nwgt25"                          
    ##  [527] "nwgt75"                           "nwgt125"                         
    ##  [529] "nwgt175"                          "nwgt26"                          
    ##  [531] "nwgt76"                           "nwgt126"                         
    ##  [533] "nwgt176"                          "nwgt27"                          
    ##  [535] "nwgt77"                           "nwgt127"                         
    ##  [537] "nwgt177"                          "nwgt28"                          
    ##  [539] "nwgt78"                           "nwgt128"                         
    ##  [541] "nwgt178"                          "nwgt29"                          
    ##  [543] "nwgt79"                           "nwgt129"                         
    ##  [545] "nwgt179"                          "nwgt30"                          
    ##  [547] "nwgt80"                           "nwgt130"                         
    ##  [549] "nwgt180"                          "nwgt31"                          
    ##  [551] "nwgt81"                           "nwgt131"                         
    ##  [553] "nwgt181"                          "nwgt32"                          
    ##  [555] "nwgt82"                           "nwgt132"                         
    ##  [557] "nwgt182"                          "nwgt33"                          
    ##  [559] "nwgt83"                           "nwgt133"                         
    ##  [561] "nwgt183"                          "nwgt34"                          
    ##  [563] "nwgt84"                           "nwgt134"                         
    ##  [565] "nwgt184"                          "nwgt35"                          
    ##  [567] "nwgt85"                           "nwgt135"                         
    ##  [569] "nwgt185"                          "nwgt36"                          
    ##  [571] "nwgt86"                           "nwgt136"                         
    ##  [573] "nwgt186"                          "nwgt37"                          
    ##  [575] "nwgt87"                           "nwgt137"                         
    ##  [577] "nwgt187"                          "nwgt38"                          
    ##  [579] "nwgt88"                           "nwgt138"                         
    ##  [581] "nwgt188"                          "nwgt39"                          
    ##  [583] "nwgt89"                           "nwgt139"                         
    ##  [585] "nwgt189"                          "nwgt40"                          
    ##  [587] "nwgt90"                           "nwgt140"                         
    ##  [589] "nwgt190"                          "nwgt41"                          
    ##  [591] "nwgt91"                           "nwgt141"                         
    ##  [593] "nwgt191"                          "nwgt42"                          
    ##  [595] "nwgt92"                           "nwgt142"                         
    ##  [597] "nwgt192"                          "nwgt43"                          
    ##  [599] "nwgt93"                           "nwgt143"                         
    ##  [601] "nwgt193"                          "nwgt44"                          
    ##  [603] "nwgt94"                           "nwgt144"                         
    ##  [605] "nwgt194"                          "nwgt45"                          
    ##  [607] "nwgt95"                           "nwgt145"                         
    ##  [609] "nwgt195"                          "nwgt46"                          
    ##  [611] "nwgt96"                           "nwgt146"                         
    ##  [613] "nwgt196"                          "nwgt47"                          
    ##  [615] "nwgt97"                           "nwgt147"                         
    ##  [617] "nwgt197"                          "nwgt48"                          
    ##  [619] "nwgt98"                           "nwgt148"                         
    ##  [621] "nwgt198"                          "nwgt49"                          
    ##  [623] "nwgt99"                           "nwgt149"                         
    ##  [625] "nwgt199"                          "nwgt50"                          
    ##  [627] "nwgt100"                          "nwgt150"                         
    ##  [629] "nwgt200"                          "cycles"                          
    ##  [631] "cancerlotofeffort"                "cancerfrustrated"                
    ##  [633] "cancerconcernedquality"           "cancertoohardunderstand"         
    ##  [635] "cancerconfidentgethealthinf"      "cancertrustdoctor"               
    ##  [637] "cancertrustfamily"                "cancertrustnewsmag"              
    ##  [639] "cancertrustradio"                 "cancertrustinternet"             
    ##  [641] "cancertrusttelevision"            "cancertrustgov"                  
    ##  [643] "cancertrustcharities"             "cancertrustreligiousorgs"        
    ##  [645] "strongneedcancerinfo"             "strongneedcancerinfo_os"         
    ##  [647] "electronic_lookedassistance"      "havedevice_none"                 
    ##  [649] "havedevice_cat"                   "everofferedaccessrec"            
    ##  [651] "whooffered_hcp"                   "whooffered_insurer"              
    ##  [653] "whooffered_other"                 "whooffered_other_os"             
    ##  [655] "whooffered_cat"                   "caregiving_anotherfam"           
    ##  [657] "caregiving_professional"          "caregiving_hoursperweek2"        
    ##  [659] "caregiving_howlong"               "caregiving_reside"               
    ##  [661] "caregiving_bedschairs"            "caregiving_dressing"             
    ##  [663] "caregiving_toilet"                "caregiving_incontinence"         
    ##  [665] "caregiving_bathing"               "caregiving_mealprep"             
    ##  [667] "caregiving_feeding"               "caregiving_finances"             
    ##  [669] "caregiving_shopping"              "caregiving_housework"            
    ##  [671] "caregiving_transportation"        "caregivingactivities_cat"        
    ##  [673] "caregiving_medtasks"              "caregiving_communicatehcp"       
    ##  [675] "caregiving_arrangesvcs"           "caregiving_spendtime"            
    ##  [677] "caregivingmedact_cat"             "caregiving_accessmedrec"         
    ##  [679] "caregiver_medtrain"               "caregiver_accesshelp"            
    ##  [681] "caregiver_respitecare"            "caregiver_supportgroup"          
    ##  [683] "caregiver_counseling"             "caregivertraining_inperson"      
    ##  [685] "caregivertraining_hotline"        "caregivertraining_readingmat"    
    ##  [687] "caregivertraining_onlinevideo"    "caregivertraining_virtual"       
    ##  [689] "caregivertraining_cat"            "knowledgepalliativecare"         
    ##  [691] "pcgoal_helpfamcope"               "pcgoal_socemotsupport"           
    ##  [693] "pcgoal_managesymptoms"            "pcgoal_moretime"                 
    ##  [695] "pcstrongneedinfo"                 "pctrustinfo"                     
    ##  [697] "pcmeansgivingup"                  "pcobligatedtoinform"             
    ##  [699] "pcstoptreatments"                 "pchospicecare"                   
    ##  [701] "pcthinkdeath"                     "emotionalsupport2"               
    ##  [703] "talkhealthfriends2"               "helppreparingmeals"              
    ##  [705] "helptransportdoctor"              "helpdailychores2"                
    ##  [707] "helprunerrands"                   "influencecancer_obesity"         
    ##  [709] "influencecancer_eatinghealthy"    "influencecancer_regexercise"     
    ##  [711] "noticecalorieinfoonmenu"          "understandcalorieinfo"           
    ##  [713] "calorieinfo_fewercalories"        "calorieinfo_morecalories"        
    ##  [715] "calorieinfo_feweritems"           "calorieinfo_smallersizes"        
    ##  [717] "calorieinfo_moreitems"            "calorieinfo_largersizes"         
    ##  [719] "averagecaloriesperday"            "averagecaloriesperday_dk"        
    ##  [721] "drinkdaysperweek"                 "drinksperday"                    
    ##  [723] "howlongmoderateexerciseminutes"   "averagetimesitting"              
    ##  [725] "timesusedtanningbed"              "spendtimeinsuntanning"           
    ##  [727] "hcpadvisedlimitingsun"            "suneffectafter1hour"             
    ##  [729] "seenfederalcourttobaccomessages"  "tobaccomessages_hesmoking"       
    ##  [731] "tobaccomessages_hesecondhand"     "tobaccomessages_addictiveness"   
    ##  [733] "tobaccomessages_enhancedelivery"  "tobaccomessages_lowtarlight"     
    ##  [735] "tobaccomessages_cat"              "evertestedcolonca"               
    ##  [737] "freqworrycanceragain"             "imaginecanceragain"              
    ##  [739] "freqworrycancernodx"              "imaginecancer"                   
    ##  [741] "familiarfamilycancer"             "familycancer_mother"             
    ##  [743] "familycancer_father"              "familycancer_sister"             
    ##  [745] "familycancer_brother"             "familycancer_children"           
    ##  [747] "familycancer_othfam"              "familycancer_hcp"                
    ##  [749] "familycancer_none"                "familycancer_cat"                
    ##  [751] "confidentfamilyhistory"           "mailsurveytimemin"               
    ##  [753] "mailsurveytimehrs"                "form_name"                       
    ##  [755] "avgdrinksperweek"                 "dra"                             
    ##  [757] "treatment_h5c3"                   "electronic_ecigharms"            
    ##  [759] "wearabledevtrackhealth"           "freqweardevtrackhealth"          
    ##  [761] "willingsharedata_hcp"             "willingsharedata_fam"            
    ##  [763] "otherdevtrackhealth2"             "freqgourgentcare"                
    ##  [765] "qualitycareurgentcare"            "notaccessed_loginprob"           
    ##  [767] "notaccessed_uncomfortable"        "notaccessed_multiplerec"         
    ##  [769] "accessusinghealthapp"             "onlinerecclinnotes"              
    ##  [771] "avoiddoc"                         "weightperception"                
    ##  [773] "weightintention"                  "changethinking"                  
    ##  [775] "considerfuture"                   "hcpalcoholconsequences"          
    ##  [777] "enjoyexercise"                    "regexercise_pressure"            
    ##  [779] "regexercise_appearance"           "regexercise_guilt"               
    ##  [781] "regexercise_enjoyment"            "govparec_hcp"                    
    ##  [783] "govparec_internet"                "govparec_tv"                     
    ##  [785] "govparec_magazine"                "exrec_increasedex"               
    ##  [787] "exrec_decreasedex"                "exrec_changedex"                 
    ##  [789] "exrec_lookedinfo"                 "exrec_nochange"                  
    ##  [791] "exrec_notheard"                   "exrec_cat"                       
    ##  [793] "physact_helpsleep"                "physact_reduceanxiety"           
    ##  [795] "physact_reducepain"               "averagesleepnight"               
    ##  [797] "averagesleepquality"              "morningnightperson"              
    ##  [799] "enjoytimeinsun"                   "timessunburned"                  
    ##  [801] "sunburned_joboutside"             "sunburned_homeoutside"           
    ##  [803] "sunburned_sunbathing"             "sunburned_swimming"              
    ##  [805] "sunburned_exercise"               "sunburned_sportingevent"         
    ##  [807] "sunburned_outdoorevent"           "sunburned_daytoday"              
    ##  [809] "sunburned_other"                  "sunburned_dk"                    
    ##  [811] "sunburnedact_cat"                 "sunburned_spf15"                 
    ##  [813] "sunburned_protclothing"           "sunburned_shade"                 
    ##  [815] "sunburned_none"                   "sunburned_dontremember"          
    ##  [817] "sunburnedprot_cat"                "sunburned_alcohol"               
    ##  [819] "smokedayecig"                     "nicotinewantsmoke"               
    ##  [821] "nicotinecausecancer"              "nicotineaddictionconcern"        
    ##  [823] "lownicotineharmful"               "lownicotineaddictive"            
    ##  [825] "seenfederalcourttobaccomessages2" "heardhepc"                       
    ##  [827] "chancegetcancernodx"              "cancersign_unexpbleeding"        
    ##  [829] "cancersign_bowelbladderchange"    "cancersign_unexpweightloss"      
    ##  [831] "influencecancer_eatingfiber"      "influencecancer_processedmeat"   
    ##  [833] "influencecancer_eatingfruitveg"   "hhadultgender6"                  
    ##  [835] "hhadultage6"                      "hhadultmob6"                     
    ##  [837] "incomefeelings"                   "prompt"                          
    ##  [839] "mailnum"                          "tg_all_finwt1"                   
    ##  [841] "tg_all_finwt2"                    "tg_all_finwt3"                   
    ##  [843] "tg_all_finwt4"                    "tg_all_finwt5"                   
    ##  [845] "tg_all_finwt6"                    "tg_all_finwt7"                   
    ##  [847] "tg_all_finwt8"                    "tg_all_finwt9"                   
    ##  [849] "tg_all_finwt10"                   "tg_all_finwt11"                  
    ##  [851] "tg_all_finwt12"                   "tg_all_finwt13"                  
    ##  [853] "tg_all_finwt14"                   "tg_all_finwt15"                  
    ##  [855] "tg_all_finwt16"                   "tg_all_finwt17"                  
    ##  [857] "tg_all_finwt18"                   "tg_all_finwt19"                  
    ##  [859] "tg_all_finwt20"                   "tg_all_finwt21"                  
    ##  [861] "tg_all_finwt22"                   "tg_all_finwt23"                  
    ##  [863] "tg_all_finwt24"                   "tg_all_finwt25"                  
    ##  [865] "tg_all_finwt26"                   "tg_all_finwt27"                  
    ##  [867] "tg_all_finwt28"                   "tg_all_finwt29"                  
    ##  [869] "tg_all_finwt30"                   "tg_all_finwt31"                  
    ##  [871] "tg_all_finwt32"                   "tg_all_finwt33"                  
    ##  [873] "tg_all_finwt34"                   "tg_all_finwt35"                  
    ##  [875] "tg_all_finwt36"                   "tg_all_finwt37"                  
    ##  [877] "tg_all_finwt38"                   "tg_all_finwt39"                  
    ##  [879] "tg_all_finwt40"                   "tg_all_finwt41"                  
    ##  [881] "tg_all_finwt42"                   "tg_all_finwt43"                  
    ##  [883] "tg_all_finwt44"                   "tg_all_finwt45"                  
    ##  [885] "tg_all_finwt46"                   "tg_all_finwt47"                  
    ##  [887] "tg_all_finwt48"                   "tg_all_finwt49"                  
    ##  [889] "tg_all_finwt50"                   "tg_all_finwt0"                   
    ##  [891] "tg1_finwt1"                       "tg1_finwt2"                      
    ##  [893] "tg1_finwt3"                       "tg1_finwt4"                      
    ##  [895] "tg1_finwt5"                       "tg1_finwt6"                      
    ##  [897] "tg1_finwt7"                       "tg1_finwt8"                      
    ##  [899] "tg1_finwt9"                       "tg1_finwt10"                     
    ##  [901] "tg1_finwt11"                      "tg1_finwt12"                     
    ##  [903] "tg1_finwt13"                      "tg1_finwt14"                     
    ##  [905] "tg1_finwt15"                      "tg1_finwt16"                     
    ##  [907] "tg1_finwt17"                      "tg1_finwt18"                     
    ##  [909] "tg1_finwt19"                      "tg1_finwt20"                     
    ##  [911] "tg1_finwt21"                      "tg1_finwt22"                     
    ##  [913] "tg1_finwt23"                      "tg1_finwt24"                     
    ##  [915] "tg1_finwt25"                      "tg1_finwt26"                     
    ##  [917] "tg1_finwt27"                      "tg1_finwt28"                     
    ##  [919] "tg1_finwt29"                      "tg1_finwt30"                     
    ##  [921] "tg1_finwt31"                      "tg1_finwt32"                     
    ##  [923] "tg1_finwt33"                      "tg1_finwt34"                     
    ##  [925] "tg1_finwt35"                      "tg1_finwt36"                     
    ##  [927] "tg1_finwt37"                      "tg1_finwt38"                     
    ##  [929] "tg1_finwt39"                      "tg1_finwt40"                     
    ##  [931] "tg1_finwt41"                      "tg1_finwt42"                     
    ##  [933] "tg1_finwt43"                      "tg1_finwt44"                     
    ##  [935] "tg1_finwt45"                      "tg1_finwt46"                     
    ##  [937] "tg1_finwt47"                      "tg1_finwt48"                     
    ##  [939] "tg1_finwt49"                      "tg1_finwt50"                     
    ##  [941] "tg1_finwt0"                       "tg2_finwt1"                      
    ##  [943] "tg2_finwt2"                       "tg2_finwt3"                      
    ##  [945] "tg2_finwt4"                       "tg2_finwt5"                      
    ##  [947] "tg2_finwt6"                       "tg2_finwt7"                      
    ##  [949] "tg2_finwt8"                       "tg2_finwt9"                      
    ##  [951] "tg2_finwt10"                      "tg2_finwt11"                     
    ##  [953] "tg2_finwt12"                      "tg2_finwt13"                     
    ##  [955] "tg2_finwt14"                      "tg2_finwt15"                     
    ##  [957] "tg2_finwt16"                      "tg2_finwt17"                     
    ##  [959] "tg2_finwt18"                      "tg2_finwt19"                     
    ##  [961] "tg2_finwt20"                      "tg2_finwt21"                     
    ##  [963] "tg2_finwt22"                      "tg2_finwt23"                     
    ##  [965] "tg2_finwt24"                      "tg2_finwt25"                     
    ##  [967] "tg2_finwt26"                      "tg2_finwt27"                     
    ##  [969] "tg2_finwt28"                      "tg2_finwt29"                     
    ##  [971] "tg2_finwt30"                      "tg2_finwt31"                     
    ##  [973] "tg2_finwt32"                      "tg2_finwt33"                     
    ##  [975] "tg2_finwt34"                      "tg2_finwt35"                     
    ##  [977] "tg2_finwt36"                      "tg2_finwt37"                     
    ##  [979] "tg2_finwt38"                      "tg2_finwt39"                     
    ##  [981] "tg2_finwt40"                      "tg2_finwt41"                     
    ##  [983] "tg2_finwt42"                      "tg2_finwt43"                     
    ##  [985] "tg2_finwt44"                      "tg2_finwt45"                     
    ##  [987] "tg2_finwt46"                      "tg2_finwt47"                     
    ##  [989] "tg2_finwt48"                      "tg2_finwt49"                     
    ##  [991] "tg2_finwt50"                      "tg2_finwt0"                      
    ##  [993] "tg3_finwt1"                       "tg3_finwt2"                      
    ##  [995] "tg3_finwt3"                       "tg3_finwt4"                      
    ##  [997] "tg3_finwt5"                       "tg3_finwt6"                      
    ##  [999] "tg3_finwt7"                       "tg3_finwt8"                      
    ## [1001] "tg3_finwt9"                       "tg3_finwt10"                     
    ## [1003] "tg3_finwt11"                      "tg3_finwt12"                     
    ## [1005] "tg3_finwt13"                      "tg3_finwt14"                     
    ## [1007] "tg3_finwt15"                      "tg3_finwt16"                     
    ## [1009] "tg3_finwt17"                      "tg3_finwt18"                     
    ## [1011] "tg3_finwt19"                      "tg3_finwt20"                     
    ## [1013] "tg3_finwt21"                      "tg3_finwt22"                     
    ## [1015] "tg3_finwt23"                      "tg3_finwt24"                     
    ## [1017] "tg3_finwt25"                      "tg3_finwt26"                     
    ## [1019] "tg3_finwt27"                      "tg3_finwt28"                     
    ## [1021] "tg3_finwt29"                      "tg3_finwt30"                     
    ## [1023] "tg3_finwt31"                      "tg3_finwt32"                     
    ## [1025] "tg3_finwt33"                      "tg3_finwt34"                     
    ## [1027] "tg3_finwt35"                      "tg3_finwt36"                     
    ## [1029] "tg3_finwt37"                      "tg3_finwt38"                     
    ## [1031] "tg3_finwt39"                      "tg3_finwt40"                     
    ## [1033] "tg3_finwt41"                      "tg3_finwt42"                     
    ## [1035] "tg3_finwt43"                      "tg3_finwt44"                     
    ## [1037] "tg3_finwt45"                      "tg3_finwt46"                     
    ## [1039] "tg3_finwt47"                      "tg3_finwt48"                     
    ## [1041] "tg3_finwt49"                      "tg3_finwt50"                     
    ## [1043] "tg3_finwt0"                       "h5c3_nwgt1"                      
    ## [1045] "h5c3_nwgt2"                       "h5c3_nwgt3"                      
    ## [1047] "h5c3_nwgt4"                       "h5c3_nwgt5"                      
    ## [1049] "h5c3_nwgt6"                       "h5c3_nwgt7"                      
    ## [1051] "h5c3_nwgt8"                       "h5c3_nwgt9"                      
    ## [1053] "h5c3_nwgt10"                      "h5c3_nwgt11"                     
    ## [1055] "h5c3_nwgt12"                      "h5c3_nwgt13"                     
    ## [1057] "h5c3_nwgt14"                      "h5c3_nwgt15"                     
    ## [1059] "h5c3_nwgt16"                      "h5c3_nwgt17"                     
    ## [1061] "h5c3_nwgt18"                      "h5c3_nwgt19"                     
    ## [1063] "h5c3_nwgt20"                      "h5c3_nwgt21"                     
    ## [1065] "h5c3_nwgt22"                      "h5c3_nwgt23"                     
    ## [1067] "h5c3_nwgt24"                      "h5c3_nwgt25"                     
    ## [1069] "h5c3_nwgt26"                      "h5c3_nwgt27"                     
    ## [1071] "h5c3_nwgt28"                      "h5c3_nwgt29"                     
    ## [1073] "h5c3_nwgt30"                      "h5c3_nwgt31"                     
    ## [1075] "h5c3_nwgt32"                      "h5c3_nwgt33"                     
    ## [1077] "h5c3_nwgt34"                      "h5c3_nwgt35"                     
    ## [1079] "h5c3_nwgt36"                      "h5c3_nwgt37"                     
    ## [1081] "h5c3_nwgt38"                      "h5c3_nwgt39"                     
    ## [1083] "h5c3_nwgt40"                      "h5c3_nwgt41"                     
    ## [1085] "h5c3_nwgt42"                      "h5c3_nwgt43"                     
    ## [1087] "h5c3_nwgt44"                      "h5c3_nwgt45"                     
    ## [1089] "h5c3_nwgt46"                      "h5c3_nwgt47"                     
    ## [1091] "h5c3_nwgt48"                      "h5c3_nwgt49"                     
    ## [1093] "h5c3_nwgt50"                      "h5c3_nwgt51"                     
    ## [1095] "h5c3_nwgt52"                      "h5c3_nwgt53"                     
    ## [1097] "h5c3_nwgt54"                      "h5c3_nwgt55"                     
    ## [1099] "h5c3_nwgt56"                      "h5c3_nwgt57"                     
    ## [1101] "h5c3_nwgt58"                      "h5c3_nwgt59"                     
    ## [1103] "h5c3_nwgt60"                      "h5c3_nwgt61"                     
    ## [1105] "h5c3_nwgt62"                      "h5c3_nwgt63"                     
    ## [1107] "h5c3_nwgt64"                      "h5c3_nwgt65"                     
    ## [1109] "h5c3_nwgt66"                      "h5c3_nwgt67"                     
    ## [1111] "h5c3_nwgt68"                      "h5c3_nwgt69"                     
    ## [1113] "h5c3_nwgt70"                      "h5c3_nwgt71"                     
    ## [1115] "h5c3_nwgt72"                      "h5c3_nwgt73"                     
    ## [1117] "h5c3_nwgt74"                      "h5c3_nwgt75"                     
    ## [1119] "h5c3_nwgt76"                      "h5c3_nwgt77"                     
    ## [1121] "h5c3_nwgt78"                      "h5c3_nwgt79"                     
    ## [1123] "h5c3_nwgt80"                      "h5c3_nwgt81"                     
    ## [1125] "h5c3_nwgt82"                      "h5c3_nwgt83"                     
    ## [1127] "h5c3_nwgt84"                      "h5c3_nwgt85"                     
    ## [1129] "h5c3_nwgt86"                      "h5c3_nwgt87"                     
    ## [1131] "h5c3_nwgt88"                      "h5c3_nwgt89"                     
    ## [1133] "h5c3_nwgt90"                      "h5c3_nwgt91"                     
    ## [1135] "h5c3_nwgt92"                      "h5c3_nwgt93"                     
    ## [1137] "h5c3_nwgt94"                      "h5c3_nwgt95"                     
    ## [1139] "h5c3_nwgt96"                      "h5c3_nwgt97"                     
    ## [1141] "h5c3_nwgt98"                      "h5c3_nwgt99"                     
    ## [1143] "h5c3_nwgt100"                     "h5c3_nwgt101"                    
    ## [1145] "h5c3_nwgt102"                     "h5c3_nwgt103"                    
    ## [1147] "h5c3_nwgt104"                     "h5c3_nwgt105"                    
    ## [1149] "h5c3_nwgt106"                     "h5c3_nwgt107"                    
    ## [1151] "h5c3_nwgt108"                     "h5c3_nwgt109"                    
    ## [1153] "h5c3_nwgt110"                     "h5c3_nwgt111"                    
    ## [1155] "h5c3_nwgt112"                     "h5c3_nwgt113"                    
    ## [1157] "h5c3_nwgt114"                     "h5c3_nwgt115"                    
    ## [1159] "h5c3_nwgt116"                     "h5c3_nwgt117"                    
    ## [1161] "h5c3_nwgt118"                     "h5c3_nwgt119"                    
    ## [1163] "h5c3_nwgt120"                     "h5c3_nwgt121"                    
    ## [1165] "h5c3_nwgt122"                     "h5c3_nwgt123"                    
    ## [1167] "h5c3_nwgt124"                     "h5c3_nwgt125"                    
    ## [1169] "h5c3_nwgt126"                     "h5c3_nwgt127"                    
    ## [1171] "h5c3_nwgt128"                     "h5c3_nwgt129"                    
    ## [1173] "h5c3_nwgt130"                     "h5c3_nwgt131"                    
    ## [1175] "h5c3_nwgt132"                     "h5c3_nwgt133"                    
    ## [1177] "h5c3_nwgt134"                     "h5c3_nwgt135"                    
    ## [1179] "h5c3_nwgt136"                     "h5c3_nwgt137"                    
    ## [1181] "h5c3_nwgt138"                     "h5c3_nwgt139"                    
    ## [1183] "h5c3_nwgt140"                     "h5c3_nwgt141"                    
    ## [1185] "h5c3_nwgt142"                     "h5c3_nwgt143"                    
    ## [1187] "h5c3_nwgt144"                     "h5c3_nwgt145"                    
    ## [1189] "h5c3_nwgt146"                     "h5c3_nwgt147"                    
    ## [1191] "h5c3_nwgt148"                     "h5c3_nwgt149"                    
    ## [1193] "h5c3_nwgt150"                     "h5c3_nwgt0"                      
    ## [1195] "treatment_h5c4"                   "pandemic"                        
    ## [1197] "internetspeed"                    "usedhealthwellnessapps"          
    ## [1199] "willingsharedata_yourfamily"      "willingsharedata_yourfriends"    
    ## [1201] "howaccessonlinerecord"            "caregiving_accessmedrec2"        
    ## [1203] "heardgentest_ancestry"            "heardgentest_healthrisk"         
    ## [1205] "heardgentest_cancerrisk"          "heardgentest_other"              
    ## [1207] "heardgentest_other_os"            "heardgentest_notsure"            
    ## [1209] "heardgentest_none"                "heardgentest_cat"                
    ## [1211] "testsource_ppr"                   "testsource_mag"                  
    ## [1213] "testsource_radio"                 "testsource_hcp"                  
    ## [1215] "testsource_counselor"             "testsource_family"               
    ## [1217] "testsource_friend"                "testsource_socmed"               
    ## [1219] "testsource_tv"                    "testsource_www"                  
    ## [1221] "testsource_other"                 "testsource_other_os"             
    ## [1223] "testsource_notheard"              "testsource_notsure"              
    ## [1225] "testsource_cat"                   "hadtest2_ancestry"               
    ## [1227] "hadtest2_healthrisk"              "hadtest2_cancerrisk"             
    ## [1229] "hadtest2_other"                   "hadtest2_other_os"               
    ## [1231] "hadtest2_notsure"                 "hadtest2_none"                   
    ## [1233] "hadtest2_cat"                     "sharedres2_hcp"                  
    ## [1235] "sharedres2_counselor"             "sharedres2_spouse"               
    ## [1237] "sharedres2_parent"                "sharedres2_sibling"              
    ## [1239] "sharedres2_child"                 "sharedres2_friend"               
    ## [1241] "sharedres2_other"                 "sharedres2_notshared"            
    ## [1243] "sharedres2_cat"                   "undgentest_hcp"                  
    ## [1245] "undgentest_counselor"             "undgentest_spouse"               
    ## [1247] "undgentest_parent"                "undgentest_sibling"              
    ## [1249] "undgentest_child"                 "undgentest_friend"               
    ## [1251] "undgentest_other"                 "undgentest_noone"                
    ## [1253] "undgentest_cat"                   "genetics2_obesity"               
    ## [1255] "genetics2_cancer"                 "genetics2_cardio"                
    ## [1257] "genetics2_diabetes"               "knowgenes_preventca"             
    ## [1259] "knowgenes_detectca"               "knowgenes_treatca"               
    ## [1261] "clinicaltrialknowledge"           "clintrial_helpingpeople"         
    ## [1263] "clintrial_getpaid"                "clintrial_getsupport"            
    ## [1265] "clintrial_docencouraged"          "clintrial_famencouraged"         
    ## [1267] "clintrial_getbetter"              "clintrial_newcare"               
    ## [1269] "clintrial_stdnotcovered"          "firstinfoclintrials"             
    ## [1271] "trustinfoclintrials"              "heardclintrialswebsite"          
    ## [1273] "invitedclintrial"                 "participatedclintrial"           
    ## [1275] "threatened_values"                "threatened_strengths"            
    ## [1277] "expectworst"                      "mostimportantvalues"             
    ## [1279] "junkfoodadrestrictions"           "drinksoneoccasion"               
    ## [1281] "beer_cancerrisk"                  "wine_cancerrisk"                 
    ## [1283] "liquor_cancerrisk"                "beer_heartrisk"                  
    ## [1285] "wine_heartrisk"                   "liquor_heartrisk"                
    ## [1287] "excessivealcohol_banads"          "excessivealcohol_reqwarn"        
    ## [1289] "excessivealcohol_guidelines"      "heardheatedtobacco"              
    ## [1291] "cigmeasures_movieratings"         "cigmeasures_warninglabels"       
    ## [1293] "tobaccomeasures_hideproducts"     "tobaccomeasures_hideads"         
    ## [1295] "tobaccomeasures_nosocmed"         "heardprecisionmedicine"          
    ## [1297] "highriskchangebehavior"           "geneticchangeincreasedrisk"      
    ## [1299] "influencecancer_adultweight"      "influencecancer_redmeat"         
    ## [1301] "clinicaltrialcancertx2"           "familiarfamilycancer2"           
    ## [1303] "familyeverhadcancer2"             "birthgender"                     
    ## [1305] "workfulltime"                     "occupation_employed"             
    ## [1307] "occupation_1yunemployed"          "occupation_less1yunemployed"     
    ## [1309] "occupation_homemaker"             "occupation_student"              
    ## [1311] "occupation_retired"               "occupation_disabled"             
    ## [1313] "occupation_other"                 "occupation_other_os"             
    ## [1315] "occupation_cat"                   "fulltimeocc_cat"                 
    ## [1317] "ethnicgroupbelonging"             "politicalviewpoint"              
    ## [1319] "pccscale"

``` r
pacman::p_load(tidyverse)
caregiver_small<- caregiver%>%
  select(2,143:162,191:194,291,335,336,414:420,425)
colnames(caregiver_small)
```

    ##  [1] "personid"                "caregiving_child"       
    ##  [3] "caregiving_spouse"       "caregiving_parent"      
    ##  [5] "caregiving_family"       "caregiving_friend"      
    ##  [7] "caregiving_no"           "caregivingwho_cat"      
    ##  [9] "caregiving_cancer"       "caregiving_alzheimers"  
    ## [11] "caregiving_orthomusc"    "caregiving_mentalhealth"
    ## [13] "caregiving_chroniccond"  "caregiving_neurodev"    
    ## [15] "caregiving_acutecond"    "caregiving_aging"       
    ## [17] "caregiving_notsure"      "caregiving_other"       
    ## [19] "caregiving_other_os"     "caregivingcond_cat"     
    ## [21] "caregiving_hoursperweek" "littleinterest"         
    ## [23] "hopeless"                "nervous"                
    ## [25] "worrying"                "age"                    
    ## [27] "selfgender"              "selfage"                
    ## [29] "agegrpa"                 "agegrpb"                
    ## [31] "educa"                   "educb"                  
    ## [33] "raceethn"                "raceethn5"              
    ## [35] "hhinc"                   "phq4"

``` r
## save variables of interest as new dataset
save(caregiver_small, file = "caregiver_small.Rdata")
```

``` r
## re-coding and categorizing dependent variable (phq4)

## converting phq4 to a categorical variable
# installing packages
pacman::p_load(dplyr, naniar, tidyverse)

summary(caregiver_small$phq4)
```

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##  -9.000   0.000   0.000   1.522   3.000  12.000

``` r
table(caregiver_small$phq4)
```

    ## 
    ##   -9   -7   -5    0    1    2    3    4    5    6    7    8    9   10   11   12 
    ##  524   12   21 7744 1890 1611 1035 1109  438  376  290  313  197  143  109  280

``` r
# recode missing phq4 values to NA
caregiver_small_clean<- caregiver_small %>%
  replace_with_na(replace = list(phq4 = c(-9, -7, -5)))
# delete those with missing phq4


# Categorize phq4 into binary varibale (normal and psychological distress)
caregiver_small_clean<-caregiver_small_clean%>%
  mutate(phq4_cat= if_else(phq4<3, 0,
                           if_else(phq4>2,1,NULL)))
table(caregiver_small_clean$phq4, useNA = "always")
```

    ## 
    ##    0    1    2    3    4    5    6    7    8    9   10   11   12 <NA> 
    ## 7744 1890 1611 1035 1109  438  376  290  313  197  143  109  280  557

``` r
table(caregiver_small_clean$phq4_cat, useNA = "always")
```

    ## 
    ##     0     1  <NA> 
    ## 11245  4290   557

``` r
class(caregiver_small_clean$phq4_cat)
```

    ## [1] "numeric"

``` r
caregiver_small_clean$phq4_cat<- as.factor(caregiver_small_clean$phq4_cat)

## Convert to factor and label categories of phq4_cat
caregiver_small_clean$phq4_cat <- factor(caregiver_small_clean$phq4_cat,
levels = c(0,1),
labels = c("Normal", "Psychological distress"))
```

``` r
#### Recoding independent variables 

### Medical caregiving (caregiving_no)
##recoding missing values to NA
table(caregiver_small_clean$caregiving_no)
```

    ## 
    ##    -9    -7     1     2 
    ##   530     6 13094  2462

``` r
caregiver_small_clean<- caregiver_small_clean %>%
  replace_with_na(replace = list(caregiving_no = c(-9, -7)))

class(caregiver_small_clean$caregiving_no)
```

    ## [1] "haven_labelled" "vctrs_vctr"     "double"

``` r
## converting variable to factor and labelling values
caregiver_small_clean$caregiving_no <- factor(caregiver_small_clean$caregiving_no,
levels = c(1,2),
labels = c("Not a caregiver", "Caregiver"))

##Renaming variable to Cargiving
colnames(caregiver_small_clean)
```

    ##  [1] "personid"                "caregiving_child"       
    ##  [3] "caregiving_spouse"       "caregiving_parent"      
    ##  [5] "caregiving_family"       "caregiving_friend"      
    ##  [7] "caregiving_no"           "caregivingwho_cat"      
    ##  [9] "caregiving_cancer"       "caregiving_alzheimers"  
    ## [11] "caregiving_orthomusc"    "caregiving_mentalhealth"
    ## [13] "caregiving_chroniccond"  "caregiving_neurodev"    
    ## [15] "caregiving_acutecond"    "caregiving_aging"       
    ## [17] "caregiving_notsure"      "caregiving_other"       
    ## [19] "caregiving_other_os"     "caregivingcond_cat"     
    ## [21] "caregiving_hoursperweek" "littleinterest"         
    ## [23] "hopeless"                "nervous"                
    ## [25] "worrying"                "age"                    
    ## [27] "selfgender"              "selfage"                
    ## [29] "agegrpa"                 "agegrpb"                
    ## [31] "educa"                   "educb"                  
    ## [33] "raceethn"                "raceethn5"              
    ## [35] "hhinc"                   "phq4"                   
    ## [37] "phq4_cat"

``` r
names(caregiver_small_clean)[7]<-c("Caregiving")
table(caregiver_small_clean$Caregiving)
```

    ## 
    ## Not a caregiver       Caregiver 
    ##           13094            2462

``` r
### Age
table(caregiver_small_clean$selfage)
```

    ## 
    ##   -9   -7   -4   18   19   20   21   22   23   24   25   26   27   28   29   30 
    ## 1278   43   13   42   37   51   56   57   88   98  107  107  129  149  148  145 
    ##   31   32   33   34   35   36   37   38   39   40   41   42   43   44   45   46 
    ##  153  187  168  165  195  158  172  179  193  197  166  201  198  165  223  189 
    ##   47   48   49   50   51   52   53   54   55   56   57   58   59   60   61   62 
    ##  202  207  209  265  232  285  287  280  300  304  347  345  329  354  318  373 
    ##   63   64   65   66   67   68   69   70   71   72   73   74   75   76   77   78 
    ##  358  368  409  371  355  361  322  354  287  319  241  225  237  209  208  169 
    ##   79   80   81   82   83   84   85   86   87   88   89   90   91   92   93   94 
    ##  139  141  111  122   87   85   76   98   72   59   42   39   27   37   28   11 
    ##   95   96   97   98   99  100  101  102  104 
    ##    8    5    5    6    2    1    2    1    1

``` r
#recode missing values as NA
caregiver_small_clean<- caregiver_small_clean %>%
  replace_with_na(replace = list(selfage = c(-9, -7, -4)))
#creating age group categories
caregiver_small_clean <- caregiver_small_clean%>%
  mutate(
    age_group = dplyr::case_when(
      selfage >= 18 & selfage <=34 ~ 0,
      selfage >= 35 & selfage <= 49 ~ 1,
      selfage >= 50 & selfage <= 64 ~ 2,
      selfage >= 65 & selfage <= 74 ~ 3,
      selfage >= 75 ~ 4
    ),
    age_group = factor(age_group, 0:4, c("18-34", "35-49", "50-64", "65-74","75+" ))) #convert to factor 

table(caregiver_small_clean$age_group)
```

    ## 
    ## 18-34 35-49 50-64 65-74   75+ 
    ##  1887  2854  4745  3244  2028

``` r
class(caregiver_small_clean$age_group)
```

    ## [1] "factor"

``` r
summary(caregiver_small_clean$age_group)
```

    ## 18-34 35-49 50-64 65-74   75+  NA's 
    ##  1887  2854  4745  3244  2028  1334

``` r
by(caregiver_small_clean$selfage, caregiver_small_clean$age_group, summary)
```

    ## caregiver_small_clean$age_group: 18-34
    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##   18.00   25.00   29.00   28.04   32.00   34.00 
    ## ------------------------------------------------------------ 
    ## caregiver_small_clean$age_group: 35-49
    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##   35.00   39.00   42.00   42.22   46.00   49.00 
    ## ------------------------------------------------------------ 
    ## caregiver_small_clean$age_group: 50-64
    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##    50.0    54.0    58.0    57.5    61.0    64.0 
    ## ------------------------------------------------------------ 
    ## caregiver_small_clean$age_group: 65-74
    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##   65.00   67.00   69.00   69.05   71.00   74.00 
    ## ------------------------------------------------------------ 
    ## caregiver_small_clean$age_group: 75+
    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##   75.00   77.00   80.00   81.16   85.00  104.00

``` r
### Gender
# converting missing values to NA
table(caregiver_small_clean$selfgender)
```

    ## 
    ##   -9   -7   -5    1    2 
    ## 1316   43    1 6159 8573

``` r
caregiver_small_clean<- caregiver_small_clean %>%
  replace_with_na(replace = list(selfgender = c(-9, -7, -5)))
#convert to factor and label
caregiver_small_clean$selfgender<- factor(caregiver_small_clean$selfgender,
levels = c(1,2),
labels = c("Male", "Female"))

## Educational status 
#converting missing values to NA 
table(caregiver_small_clean$educa)
```

    ## 
    ##   -9   -7    1    2    3    4 
    ##  412   43 1099 2898 4653 6987

``` r
caregiver_small_clean<- caregiver_small_clean %>%
  replace_with_na(replace = list(educa = c(-9, -7)))
#convert to factor and label 
caregiver_small_clean$educa<- factor(caregiver_small_clean$educa,
levels = c(1,2,3,4),
labels = c("Less than High School", "High School Graduate", "Some College","College Graduate or More"))

## Race/ethnicity
#converting missing values to NA 
table(caregiver_small_clean$raceethn5)
```

    ## 
    ##   -9   -7    1    2    3    4    5 
    ## 1605   43 9038 2011 2214  661  520

``` r
caregiver_small_clean<- caregiver_small_clean %>%
  replace_with_na(replace = list(raceethn5 = c(-9, -7)))
#convert to factor and label 
caregiver_small_clean$raceethn5<- factor(caregiver_small_clean$raceethn5,
levels = c(1,2,3,4,5),
labels = c("NH white", "NH black/African American", "Hispanic","NH Asian", "Other"))

### Household income 
#converting missing values to NA 
table(caregiver_small_clean$hhinc)
```

    ## 
    ##   -9   -7    1    2    3    4    5 
    ## 1748   49 2666 1916 1880 2537 5296

``` r
caregiver_small_clean<- caregiver_small_clean %>%
  replace_with_na(replace = list(hhinc = c(-9, -7)))
#convert to factor and label 
caregiver_small_clean$hhinc<- factor(caregiver_small_clean$hhinc,
levels = c(1,2,3,4,5),
labels = c("Less than $20,000", "$20,000 to < $35,000", "$35,000 to < $50,000","$50,000 to < $75,000", "$75,000 or More"))
```

``` r
## descriptives table 
library(table1)
```

    ## 
    ## Attaching package: 'table1'

    ## The following objects are masked from 'package:base':
    ## 
    ##     units, units<-

``` r
tbl1<-table1(~ age_group + selfgender + raceethn5 + educa + hhinc | Caregiving, data=caregiver_small_clean, overall="Total")

#saving table1 to doc
pacman::p_load(flextable,magrittr)
t1flex(tbl1) %>% 
  save_as_docx(path="caregiving_tab1.docx")
```

``` r
##logistic regression analysis 
#loading packages
pacman::p_load(odds.n.ends, blorr, lmtest, car,  broom, tidyverse, jtools, readr) 

# Un-adjusted model
table(caregiver_small_clean$Caregiving)
```

    ## 
    ## Not a caregiver       Caregiver 
    ##           13094            2462

``` r
model1<- glm(phq4_cat ~ Caregiving, data=caregiver_small_clean, family="binomial")
summary(model1) # get log results
```

    ## 
    ## Call:
    ## glm(formula = phq4_cat ~ Caregiving, family = "binomial", data = caregiver_small_clean)
    ## 
    ## Deviance Residuals: 
    ##     Min       1Q   Median       3Q      Max  
    ## -0.9116  -0.7760  -0.7760   1.4689   1.6414  
    ## 
    ## Coefficients:
    ##                     Estimate Std. Error z value Pr(>|z|)    
    ## (Intercept)         -1.04593    0.02022 -51.733  < 2e-16 ***
    ## CaregivingCaregiver  0.38256    0.04755   8.045 8.59e-16 ***
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## (Dispersion parameter for binomial family taken to be 1)
    ## 
    ##     Null deviance: 17721  on 15120  degrees of freedom
    ## Residual deviance: 17658  on 15119  degrees of freedom
    ##   (971 observations deleted due to missingness)
    ## AIC: 17662
    ## 
    ## Number of Fisher Scoring iterations: 4

``` r
odds.n.ends(model1) # get OR results
```

    ## Waiting for profiling to be done...

    ## $`Logistic regression model significance`
    ## Chi-squared        d.f.           p 
    ##      62.901           1       <.001 
    ## 
    ## $`Contingency tables (model fit): frequency predicted`
    ##                 Number observed
    ## Number predicted     1     0   Sum
    ##              1       0     0     0
    ##              0    4124 10997 15121
    ##              Sum  4124 10997 15121
    ## 
    ## $`Count R-squared (model fit): percent correctly predicted`
    ## [1] 72.72667
    ## 
    ## $`Model sensitivity`
    ## [1] 0
    ## 
    ## $`Model specificity`
    ## [1] 1
    ## 
    ## $`Predictor odds ratios and 95% CI`
    ##                            OR     2.5 %    97.5 %
    ## (Intercept)         0.3513657 0.3376717 0.3655231
    ## CaregivingCaregiver 1.4660319 1.3351776 1.6087814

``` r
#adjusted model without interaction term 
model2<- glm(phq4_cat ~ Caregiving+age_group+selfgender+raceethn5+educa+hhinc, data=caregiver_small_clean, family="binomial")
summary(model2) # get log results
```

    ## 
    ## Call:
    ## glm(formula = phq4_cat ~ Caregiving + age_group + selfgender + 
    ##     raceethn5 + educa + hhinc, family = "binomial", data = caregiver_small_clean)
    ## 
    ## Deviance Residuals: 
    ##     Min       1Q   Median       3Q      Max  
    ## -1.5688  -0.8116  -0.6596   1.1473   2.2981  
    ## 
    ## Coefficients:
    ##                                    Estimate Std. Error z value Pr(>|z|)    
    ## (Intercept)                         0.48257    0.11014   4.382 1.18e-05 ***
    ## CaregivingCaregiver                 0.33745    0.05485   6.152 7.63e-10 ***
    ## age_group35-49                     -0.22582    0.06757  -3.342 0.000831 ***
    ## age_group50-64                     -0.50480    0.06374  -7.919 2.39e-15 ***
    ## age_group65-74                     -0.98027    0.07289 -13.449  < 2e-16 ***
    ## age_group75+                       -1.02365    0.08737 -11.717  < 2e-16 ***
    ## selfgenderFemale                    0.23180    0.04343   5.337 9.46e-08 ***
    ## raceethn5NH black/African American -0.40152    0.06598  -6.085 1.16e-09 ***
    ## raceethn5Hispanic                  -0.16685    0.06109  -2.731 0.006309 ** 
    ## raceethn5NH Asian                  -0.33262    0.10750  -3.094 0.001974 ** 
    ## raceethn5Other                      0.17267    0.10693   1.615 0.106349    
    ## educaHigh School Graduate          -0.19302    0.09634  -2.003 0.045126 *  
    ## educaSome College                  -0.13830    0.09216  -1.501 0.133416    
    ## educaCollege Graduate or More      -0.33409    0.09434  -3.541 0.000398 ***
    ## hhinc$20,000 to < $35,000          -0.53730    0.07322  -7.339 2.16e-13 ***
    ## hhinc$35,000 to < $50,000          -0.72702    0.07487  -9.711  < 2e-16 ***
    ## hhinc$50,000 to < $75,000          -0.95331    0.07142 -13.349  < 2e-16 ***
    ## hhinc$75,000 or More               -1.29001    0.06721 -19.195  < 2e-16 ***
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## (Dispersion parameter for binomial family taken to be 1)
    ## 
    ##     Null deviance: 14474  on 12261  degrees of freedom
    ## Residual deviance: 13608  on 12244  degrees of freedom
    ##   (3830 observations deleted due to missingness)
    ## AIC: 13644
    ## 
    ## Number of Fisher Scoring iterations: 4

``` r
odds.n.ends(model2) # get OR results
```

    ## Waiting for profiling to be done...

    ## $`Logistic regression model significance`
    ## Chi-squared        d.f.           p 
    ##     865.856          17       <.001 
    ## 
    ## $`Contingency tables (model fit): frequency predicted`
    ##                 Number observed
    ## Number predicted     1     0   Sum
    ##              1     439   342   781
    ##              0    2959  8522 11481
    ##              Sum  3398  8864 12262
    ## 
    ## $`Count R-squared (model fit): percent correctly predicted`
    ## [1] 73.07943
    ## 
    ## $`Model sensitivity`
    ## [1] 0.1291936
    ## 
    ## $`Model specificity`
    ## [1] 0.961417
    ## 
    ## $`Predictor odds ratios and 95% CI`
    ##                                           OR     2.5 %    97.5 %
    ## (Intercept)                        1.6202317 1.3053085 2.0102354
    ## CaregivingCaregiver                1.4013626 1.2581161 1.5599307
    ## age_group35-49                     0.7978615 0.6989266 0.9108979
    ## age_group50-64                     0.6036267 0.5327773 0.6840287
    ## age_group65-74                     0.3752110 0.3251612 0.4327096
    ## age_group75+                       0.3592818 0.3024596 0.4260226
    ## selfgenderFemale                   1.2608661 1.1580906 1.3730569
    ## raceethn5NH black/African American 0.6693033 0.5876194 0.7611099
    ## raceethn5Hispanic                  0.8463229 0.7504117 0.9534860
    ## raceethn5NH Asian                  0.7170434 0.5788422 0.8824825
    ## raceethn5Other                     1.1884691 0.9621776 1.4635121
    ## educaHigh School Graduate          0.8244658 0.6828874 0.9963344
    ## educaSome College                  0.8708338 0.7273569 1.0439470
    ## educaCollege Graduate or More      0.7159923 0.5954714 0.8620019
    ## hhinc$20,000 to < $35,000          0.5843213 0.5060370 0.6742806
    ## hhinc$35,000 to < $50,000          0.4833479 0.4171910 0.5595102
    ## hhinc$50,000 to < $75,000          0.3854627 0.3349862 0.4432187
    ## hhinc$75,000 or More               0.2752669 0.2412430 0.3139621

``` r
### Assumptions of logistic regression 

## Linearity
# There are no continuous variables in the model so this assumption doesn't apply

## Multicollinearity
vif(model2) #there was no multicollinearity
```

    ##                GVIF Df GVIF^(1/(2*Df))
    ## Caregiving 1.025626  1        1.012732
    ## age_group  1.160194  4        1.018747
    ## selfgender 1.024702  1        1.012276
    ## raceethn5  1.162281  4        1.018976
    ## educa      1.344328  3        1.050552
    ## hhinc      1.371294  4        1.040259

``` r
## Influential observations
#plot of cooks distance 
plot(model2, which = 4, id.n = 3, col="red")
```

![](ada_final_project_files/figure-gfm/unnamed-chunk-8-1.png)<!-- -->

``` r
# cooks distance calculations 
model2.data <- augment(model2) %>%  
  mutate(index = 1:n()) 

head(model2.data)
```

    ## # A tibble: 6 × 15
    ##   .rownames phq4_cat  Careg…¹ age_g…² selfg…³ racee…⁴ educa hhinc .fitted .resid
    ##   <chr>     <fct>     <fct>   <fct>   <fct>   <fct>   <fct> <fct>   <dbl>  <dbl>
    ## 1 1         Normal    Not a … 35-49   Female  NH whi… High… $75,…  -0.994 -0.793
    ## 2 4         Psycholo… Not a … 35-49   Female  NH whi… Some… $20,…  -0.187  1.26 
    ## 3 5         Normal    Not a … 50-64   Male    NH whi… Coll… $75,…  -1.65  -0.594
    ## 4 6         Normal    Not a … 65-74   Male    NH whi… Coll… $50,…  -1.79  -0.557
    ## 5 8         Normal    Not a … 35-49   Female  NH bla… Coll… $75,…  -1.54  -0.624
    ## 6 9         Normal    Caregi… 75+     Male    NH whi… Coll… $75,…  -1.83  -0.546
    ## # … with 5 more variables: .std.resid <dbl>, .hat <dbl>, .sigma <dbl>,
    ## #   .cooksd <dbl>, index <int>, and abbreviated variable names ¹​Caregiving,
    ## #   ²​age_group, ³​selfgender, ⁴​raceethn5

``` r
# Exclude cases with cooks distance greater than cutoff
cuttoff <- mean(model2.data$.cooksd)*3 # defines cutoff variable

Caregiver_out <- model2.data %>% # excludes observations
  filter(.cooksd<cuttoff)

nrow(Caregiver_out)/nrow(caregiver_small_clean) # check percent kept
```

    ## [1] 0.7035173

``` r
### New logistic regression model with observations excluded
model2_new<- glm(phq4_cat ~ Caregiving+age_group+selfgender+raceethn5+educa+hhinc, data=Caregiver_out, family="binomial")
summary(model2_new) # get log results
```

    ## 
    ## Call:
    ## glm(formula = phq4_cat ~ Caregiving + age_group + selfgender + 
    ##     raceethn5 + educa + hhinc, family = "binomial", data = Caregiver_out)
    ## 
    ## Deviance Residuals: 
    ##     Min       1Q   Median       3Q      Max  
    ## -1.9034  -0.7097  -0.4798  -0.1439   2.3925  
    ## 
    ## Coefficients:
    ##                                    Estimate Std. Error z value Pr(>|z|)    
    ## (Intercept)                         0.97382    0.13624   7.148 8.80e-13 ***
    ## CaregivingCaregiver                 0.29137    0.06492   4.488 7.18e-06 ***
    ## age_group35-49                     -0.32442    0.07517  -4.316 1.59e-05 ***
    ## age_group50-64                     -0.74542    0.07138 -10.443  < 2e-16 ***
    ## age_group65-74                     -1.57626    0.08692 -18.135  < 2e-16 ***
    ## age_group75+                       -3.02348    0.15619 -19.357  < 2e-16 ***
    ## selfgenderFemale                    0.43028    0.05241   8.210  < 2e-16 ***
    ## raceethn5NH black/African American -1.50868    0.09237 -16.333  < 2e-16 ***
    ## raceethn5Hispanic                  -0.71816    0.07394  -9.712  < 2e-16 ***
    ## raceethn5NH Asian                  -3.33867    0.38936  -8.575  < 2e-16 ***
    ## raceethn5Other                     -0.90899    0.16452  -5.525 3.29e-08 ***
    ## educaHigh School Graduate          -0.08144    0.12412  -0.656    0.512    
    ## educaSome College                   0.22889    0.11828   1.935    0.053 .  
    ## educaCollege Graduate or More      -0.13616    0.12163  -1.119    0.263    
    ## hhinc$20,000 to < $35,000          -1.09338    0.08732 -12.522  < 2e-16 ***
    ## hhinc$35,000 to < $50,000          -1.45121    0.09120 -15.913  < 2e-16 ***
    ## hhinc$50,000 to < $75,000          -1.79572    0.08703 -20.633  < 2e-16 ***
    ## hhinc$75,000 or More               -2.06448    0.07983 -25.862  < 2e-16 ***
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## (Dispersion parameter for binomial family taken to be 1)
    ## 
    ##     Null deviance: 11977  on 11320  degrees of freedom
    ## Residual deviance: 10050  on 11303  degrees of freedom
    ## AIC: 10086
    ## 
    ## Number of Fisher Scoring iterations: 6

``` r
odds.n.ends(model2_new) # get OR results (and more!) #make dataframe of output
```

    ## Waiting for profiling to be done...

    ## $`Logistic regression model significance`
    ## Chi-squared        d.f.           p 
    ##    1926.898          17       <.001 
    ## 
    ## $`Contingency tables (model fit): frequency predicted`
    ##                 Number observed
    ## Number predicted     1     0   Sum
    ##              1     519   438   957
    ##              0    1990  8374 10364
    ##              Sum  2509  8812 11321
    ## 
    ## $`Count R-squared (model fit): percent correctly predicted`
    ## [1] 78.55313
    ## 
    ## $`Model sensitivity`
    ## [1] 0.2068553
    ## 
    ## $`Model specificity`
    ## [1] 0.9502951
    ## 
    ## $`Predictor odds ratios and 95% CI`
    ##                                            OR      2.5 %     97.5 %
    ## (Intercept)                        2.64803124 2.02614749 3.45685194
    ## CaregivingCaregiver                1.33826158 1.17774301 1.51910466
    ## age_group35-49                     0.72294506 0.62390034 0.83773928
    ## age_group50-64                     0.47453692 0.41258464 0.54581573
    ## age_group65-74                     0.20674784 0.17421339 0.24495097
    ## age_group75+                       0.04863177 0.03548291 0.06551300
    ## selfgenderFemale                   1.53769223 1.38793371 1.70452389
    ## raceethn5NH black/African American 0.22120242 0.18414425 0.26451843
    ## raceethn5Hispanic                  0.48764849 0.42139760 0.56311471
    ## raceethn5NH Asian                  0.03548425 0.01497084 0.07056089
    ## raceethn5Other                     0.40293197 0.28948343 0.55218800
    ## educaHigh School Graduate          0.92178774 0.72358185 1.17729217
    ## educaSome College                  1.25720759 0.99863989 1.58803773
    ## educaCollege Graduate or More      0.87270689 0.68860369 1.10946556
    ## hhinc$20,000 to < $35,000          0.33508272 0.28213440 0.39731566
    ## hhinc$35,000 to < $50,000          0.23428704 0.19571371 0.27983659
    ## hhinc$50,000 to < $75,000          0.16600739 0.13983178 0.19669523
    ## hhinc$75,000 or More               0.12688464 0.10843486 0.14827970

``` r
## effect modification 
# adjusted model plus interaction term Caregiving*selfgender
model3<- glm(phq4_cat ~ Caregiving+age_group+selfgender+raceethn5+educa+hhinc+Caregiving*selfgender, data=Caregiver_out, family="binomial")
summary(model3) # get log results
```

    ## 
    ## Call:
    ## glm(formula = phq4_cat ~ Caregiving + age_group + selfgender + 
    ##     raceethn5 + educa + hhinc + Caregiving * selfgender, family = "binomial", 
    ##     data = Caregiver_out)
    ## 
    ## Deviance Residuals: 
    ##     Min       1Q   Median       3Q      Max  
    ## -1.9036  -0.7091  -0.4799  -0.1438   2.3927  
    ## 
    ## Coefficients:
    ##                                       Estimate Std. Error z value Pr(>|z|)    
    ## (Intercept)                           0.973110   0.136919   7.107 1.18e-12 ***
    ## CaregivingCaregiver                   0.296694   0.121555   2.441   0.0147 *  
    ## age_group35-49                       -0.324370   0.075180  -4.315 1.60e-05 ***
    ## age_group50-64                       -0.745421   0.071379 -10.443  < 2e-16 ***
    ## age_group65-74                       -1.576227   0.086919 -18.134  < 2e-16 ***
    ## age_group75+                         -3.023628   0.156221 -19.355  < 2e-16 ***
    ## selfgenderFemale                      0.431447   0.057034   7.565 3.89e-14 ***
    ## raceethn5NH black/African American   -1.508743   0.092379 -16.332  < 2e-16 ***
    ## raceethn5Hispanic                    -0.718195   0.073947  -9.712  < 2e-16 ***
    ## raceethn5NH Asian                    -3.338770   0.389362  -8.575  < 2e-16 ***
    ## raceethn5Other                       -0.909021   0.164517  -5.525 3.29e-08 ***
    ## educaHigh School Graduate            -0.081408   0.124127  -0.656   0.5119    
    ## educaSome College                     0.228908   0.118284   1.935   0.0530 .  
    ## educaCollege Graduate or More        -0.136147   0.121630  -1.119   0.2630    
    ## hhinc$20,000 to < $35,000            -1.093354   0.087320 -12.521  < 2e-16 ***
    ## hhinc$35,000 to < $50,000            -1.451218   0.091196 -15.913  < 2e-16 ***
    ## hhinc$50,000 to < $75,000            -1.795725   0.087033 -20.633  < 2e-16 ***
    ## hhinc$75,000 or More                 -2.064558   0.079841 -25.858  < 2e-16 ***
    ## CaregivingCaregiver:selfgenderFemale -0.007405   0.143043  -0.052   0.9587    
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## (Dispersion parameter for binomial family taken to be 1)
    ## 
    ##     Null deviance: 11977  on 11320  degrees of freedom
    ## Residual deviance: 10050  on 11302  degrees of freedom
    ## AIC: 10088
    ## 
    ## Number of Fisher Scoring iterations: 6

``` r
odds.n.ends(model3) # get OR results (and more!) #make dataframe of output
```

    ## Waiting for profiling to be done...

    ## $`Logistic regression model significance`
    ## Chi-squared        d.f.           p 
    ##    1926.901          18       <.001 
    ## 
    ## $`Contingency tables (model fit): frequency predicted`
    ##                 Number observed
    ## Number predicted     1     0   Sum
    ##              1     519   438   957
    ##              0    1990  8374 10364
    ##              Sum  2509  8812 11321
    ## 
    ## $`Count R-squared (model fit): percent correctly predicted`
    ## [1] 78.55313
    ## 
    ## $`Model sensitivity`
    ## [1] 0.2068553
    ## 
    ## $`Model specificity`
    ## [1] 0.9502951
    ## 
    ## $`Predictor odds ratios and 95% CI`
    ##                                              OR      2.5 %     97.5 %
    ## (Intercept)                          2.64616097 2.02199048 3.45901535
    ## CaregivingCaregiver                  1.34540314 1.05666690 1.70226445
    ## age_group35-49                       0.72298243 0.62392471 0.83779262
    ## age_group50-64                       0.47453429 0.41258214 0.54581295
    ## age_group65-74                       0.20675377 0.17421775 0.24495897
    ## age_group75+                         0.04862447 0.03547566 0.06550687
    ## selfgenderFemale                     1.53948317 1.37704998 1.72209470
    ## raceethn5NH black/African American   0.22118773 0.18412886 0.26450562
    ## raceethn5Hispanic                    0.48763183 0.42138038 0.56309905
    ## raceethn5NH Asian                    0.03548058 0.01496938 0.07055367
    ## raceethn5Other                       0.40291844 0.28947357 0.55217039
    ## educaHigh School Graduate            0.92181707 0.72360140 1.17733601
    ## educaSome College                    1.25722672 0.99865196 1.58806736
    ## educaCollege Graduate or More        0.87271407 0.68860748 1.10947783
    ## hhinc$20,000 to < $35,000            0.33509084 0.28214065 0.39732610
    ## hhinc$35,000 to < $50,000            0.23428475 0.19571174 0.27983396
    ## hhinc$50,000 to < $75,000            0.16600700 0.13983141 0.19669483
    ## hhinc$75,000 or More                 0.12687434 0.10842267 0.14827220
    ## CaregivingCaregiver:selfgenderFemale 0.99262189 0.75141915 1.31679637

``` r
# Test the hypothesis with the lrtest
lrtest(model2_new, model3)
```

    ## Likelihood ratio test
    ## 
    ## Model 1: phq4_cat ~ Caregiving + age_group + selfgender + raceethn5 + 
    ##     educa + hhinc
    ## Model 2: phq4_cat ~ Caregiving + age_group + selfgender + raceethn5 + 
    ##     educa + hhinc + Caregiving * selfgender
    ##   #Df  LogLik Df  Chisq Pr(>Chisq)
    ## 1  18 -5024.9                     
    ## 2  19 -5024.9  1 0.0027     0.9587

``` r
## the interaction effect of sex was not statistically significant and hence no stratified analysis was done.
```
