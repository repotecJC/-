import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
from scipy import stats as st

#######
#量對量#
#######

##Pearsonr

###單一值比對
##########################################################################################
def pearson_one_to_mutiple(data,compare_list,aim_data):

    from scipy import stats as st
    import pandas as pd
    
    name=[]
    correlation=[]
    p_value=[]

    for i in range (len(compare_list)) :
        (c,pv) = st.pearsonr (data[aim_data],data[compare_list[i]])
        
        name.append(compare_list[i])
        correlation.append(c)
        p_value.append(pv)

    pd.set_option('display.float_format', lambda x:'%.3f'%x) #自定義pandas
    
    result=pd.DataFrame(correlation,name,columns=['Correlation'])
    result.insert(1,'p_value',p_value)
    return result
##########################################################################################

###全部比對
##########################################################################################
def pearson_mutiple(data,compare_list):

    from scipy import stats as st
    import pandas as pd
    
    name=[]
    correlation=[]
    p_value=[]

    for i in range (len(compare_list)) :
        for j in range(len(compare_list)):
            (c,pv) = st.pearsonr (data[compare_list[i]],data[compare_list[j]])
        
        name.append(compare_list[i])
        correlation.append(c)
        p_value.append(pv)

    pd.set_option('display.float_format', lambda x:'%.3f'%x) #自定義pandas
    
    result=pd.DataFrame(correlation,name,columns=['Correlation'])
    result.insert(1,'p_value',p_value)
    return result
##########################################################################################

#######
#類對量#
#######

##T-Test

###兩個變數
##########################################################################################
def ttest_compare(data,compare_list,aim_data,category1,category2):

    from scipy import stats as st
    import pandas as pd
    
    name=[]
    t_value=[]
    p_value=[]

    for i in range (len(compare_list)) :
        (t,pv) = st.ttest_ind(data[compare_list[i]][data[aim_data]==category1],data[compare_list[i]][data[aim_data]==category2])
        
        name.append(compare_list[i])
        t_value.append(t)
        p_value.append(pv)

    pd.set_option('display.float_format', lambda x:'%.2f'%x) #自定義pandas
    
    result=pd.DataFrame(t_value,name,columns=['t_value'])
    result.insert(1,'p_value',p_value)
    return result
##########################################################################################
