# Generated tables


## Table4_pretreatment_balance

|                              |Covariate                     |Honest       |FG           |SMD   |p_t  |p_ks |
|:-----------------------------|:-----------------------------|:------------|:------------|:-----|:----|:----|
|Age (years)                   |Age (years)                   |22.68 (6.01) |25.35 (9.24) |+0.34 |.075 |.185 |
|Female (proportion)           |Female (proportion)           |0.58 (0.50)  |0.31 (0.47)  |-0.56 |.004 |.005 |
|Computer skill (1--5)         |Computer skill (1--5)         |3.23 (1.20)  |3.71 (1.17)  |+0.41 |.033 |.036 |
|Cumulative job changes (0--4) |Cumulative job changes (0--4) |0.44 (1.00)  |0.45 (0.90)  |+0.02 |.929 |.650 |
|Education (1--4)              |Education (1--4)              |1.91 (1.06)  |1.96 (1.17)  |+0.05 |.808 |.822 |
|Employment status (0--3)      |Employment status (0--3)      |1.09 (0.51)  |1.29 (0.69)  |+0.34 |.079 |.178 |

## Table5_balance_before_after_iptw

|           |Covariate               |Diff.Un |Diff.Adj |KS.Un |KS.Adj |
|:----------|:-----------------------|:-------|:--------|:-----|:------|
|age        |Age (years)             |+0.34   |+0.04    |+0.07 |+0.02  |
|female     |Female (proportion)     |-0.56   |-0.08    |+0.27 |+0.04  |
|comp_skill |Computer skill (1-5)    |+0.41   |-0.00    |+0.22 |+0.03  |
|jobchg     |Job changes (0-4)       |+0.02   |-0.04    |+0.06 |+0.04  |
|edu        |Education (1-4)         |+0.05   |-0.04    |+0.06 |+0.06  |
|emp        |Employment status (0-3) |+0.34   |+0.03    |+0.09 |+0.03  |
|prop.score |Propensity score        |+0.86   |+0.08    |+0.36 |+0.15  |

## ESS_after_iptw

|Group            |N  |ESS  |
|:----------------|:--|:----|
|Honest (H)       |57 |46.2 |
|Faking-Good (FG) |55 |48.8 |

## Table6_H1_social_desirability

|Outcome                  |ATE   |SE    |CI_low |CI_high |z     |p  |
|:------------------------|:-----|:-----|:------|:-------|:-----|:--|
|Social desirability (SD) |0.227 |0.058 |0.113  |0.34    |3.923 |0  |

## Table7_H2_primary_cursor

|Outcome                    |ATE     |SE      |CI_low   |CI_high |z      |p     |p_holm |
|:--------------------------|:-------|:-------|:--------|:-------|:------|:-----|:------|
|Trajectory deviation (H2a) |-16.156 |126.173 |-263.451 |231.138 |-0.128 |0.551 |1      |
|Movement speed (H2b)       |0.028   |0.027   |-0.024   |0.081   |1.054  |0.854 |1      |

## Table8_H2_secondary_cursor

|   |Outcome                 |ATE       |SE       |CI_low   |CI_high   |z      |p     |p_bh  |
|:--|:-----------------------|:---------|:--------|:--------|:---------|:------|:-----|:-----|
|3  |big5_mean_auc_diff      |12310.985 |6387.003 |-207.31  |24829.281 |1.928  |0.054 |0.593 |
|1  |big5_mean_init_time     |124.077   |132.882  |-136.368 |384.521   |0.934  |0.35  |0.793 |
|4  |big5_mean_max_deviation |16.815    |18.268   |-18.989  |52.62     |0.92   |0.357 |0.793 |
|6  |big5_mean_y_flips       |0.369     |0.423    |-0.46    |1.198     |0.873  |0.383 |0.793 |
|7  |big5_mean_x_axis_vel    |0.031     |0.024    |-0.017   |0.078     |1.27   |0.204 |0.793 |
|10 |big5_mean_x_axis_acc    |0         |0        |0        |0         |0.785  |0.432 |0.793 |
|2  |big5_mean_react_time    |-132.184  |306.733  |-733.371 |469.002   |-0.431 |0.667 |0.815 |
|8  |big5_mean_y_axis_vel    |0.005     |0.01     |-0.014   |0.024     |0.516  |0.606 |0.815 |
|9  |big5_mean_acc           |0         |0        |0        |0         |0.498  |0.619 |0.815 |
|5  |big5_mean_x_flips       |0.047     |0.369    |-0.676   |0.769     |0.127  |0.899 |0.902 |
|11 |big5_mean_y_axis_acc    |0         |0        |0        |0         |-0.123 |0.902 |0.902 |

## Table9_moderator_cells

|Item                      |H  |FG |Total |
|:-------------------------|:--|:--|:-----|
|Ever long-term unemployed |9  |3  |12    |
|Ever fired                |1  |3  |4     |
|Current unemployed        |2  |0  |2     |
|Combined moderator M      |11 |6  |17    |

## Table10_H3_moderation

|Outcome              |Delta    |SE      |z      |p     |
|:--------------------|:--------|:-------|:------|:-----|
|Social desirability  |0.081    |0.139   |0.584  |0.559 |
|Trajectory deviation |-685.918 |507.791 |-1.351 |0.177 |
|Movement speed       |-0.158   |0.101   |-1.562 |0.118 |

## Table11_doubly_robust

|Outcome                    |Method            |ATE     |SE      |CI_low   |CI_high |z      |p     |
|:--------------------------|:-----------------|:-------|:-------|:--------|:-------|:------|:-----|
|Social desirability (H1)   |IPTW              |0.227   |0.058   |0.113    |0.34    |3.923  |0     |
|Social desirability (H1)   |DR (cov-adj IPTW) |0.235   |0.052   |0.133    |0.337   |4.517  |0     |
|Social desirability (H1)   |AIPW              |0.239   |0.047   |0.148    |0.331   |5.134  |0     |
|Trajectory deviation (H2a) |IPTW              |-16.156 |126.173 |-263.451 |231.138 |-0.128 |0.551 |
|Trajectory deviation (H2a) |DR (cov-adj IPTW) |-28.564 |125.924 |-275.371 |218.242 |-0.227 |0.59  |
|Trajectory deviation (H2a) |AIPW              |-59.697 |118.967 |-292.867 |173.474 |-0.502 |0.692 |
|Movement speed (H2b)       |IPTW              |0.028   |0.027   |-0.024   |0.081   |1.054  |0.854 |
|Movement speed (H2b)       |DR (cov-adj IPTW) |0.032   |0.026   |-0.018   |0.082   |1.253  |0.895 |
|Movement speed (H2b)       |AIPW              |0.031   |0.024   |-0.015   |0.078   |1.312  |0.905 |

## Table12_alternative_ps

|PS                  |SD                      |Deviation                    |Speed                   |
|:-------------------|:-----------------------|:----------------------------|:-----------------------|
|Logistic GLM (main) |+0.227 [+0.113, +0.340] |-16.156 [-263.451, +231.138] |+0.028 [-0.024, +0.081] |
|CBPS                |+0.237 [+0.121, +0.352] |-24.022 [-272.872, +224.828] |+0.034 [-0.020, +0.088] |
|Entropy balancing   |+0.247 [+0.129, +0.364] |-58.120 [-327.461, +211.221] |+0.032 [-0.025, +0.089] |
|GBM                 |+0.218 [+0.110, +0.326] |-36.001 [-262.014, +190.013] |+0.023 [-0.027, +0.073] |

## Table13_bootstrap

|Outcome                    |ATE     |HC3_CI               |Boot_SE |Boot_CI              |n_rep |
|:--------------------------|:-------|:--------------------|:-------|:--------------------|:-----|
|Social desirability (H1)   |+0.227  |[+0.113, +0.340]     |0.054   |[+0.121, +0.328]     |2000  |
|Trajectory deviation (H2a) |-16.156 |[-263.451, +231.138] |123.457 |[-268.481, +200.574] |2000  |
|Movement speed (H2b)       |+0.028  |[-0.024, +0.081]     |0.024   |[-0.022, +0.074]     |2000  |
