#!/usr/bin/env python
# coding: utf-8

# In[13]:


#importing libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
get_ipython().run_line_magic('matplotlib', 'inline')


# In[14]:


#loading dataset
data1=pd.read_csv("C:/Users/user13/Documents/matches.csv")
data1.head()


# In[15]:


data1 = data1.drop(columns=["umpire3"],axis=1)
data1.head()    


# In[63]:


data2=pd.read_csv("C:/Users/user13/Documents/deviliors.csv")
data2.head()


# In[17]:


#obs 1
wins=data1.groupby("season")["winner"].value_counts()
wins   #gives winners per season


# In[24]:


#obs 2
plt.figure(figsize = (15,8))
sns.countplot(x='winner',data=data1)
plt.xticks(rotation=50)
plt.xlabel("Teams")
plt.ylabel("No of wins")
plt.show()        


# Above fig gives number of total matches won by the teams.
# Maximum no of matches wons are Royal challegers bangalore(RCB) and Chennai super kings(CSK) respectively.

# In[41]:


#obs 3
data1['win_by']=np.where(data1['win_by_runs']>0,'Bat first','Bowl first')
Win=data1.win_by.value_counts()
labels=np.array(Win.index)
sizes = Win.values
plt.figure(figsize = (8,5))
plt.pie(sizes, labels=labels,startangle=90,autopct='%1.1f%%')
plt.title('Match Result')
plt.show()        #gives pie chart for the match decision W.r.t Bat/Bowl first


# In[42]:


Toss=data1.toss_decision.value_counts()
labels=np.array(Toss.index)
sizes = Toss.values
plt.figure(figsize = (8,5))
plt.pie(sizes, labels=labels,autopct='%1.1f%%',startangle=90)
plt.title("Toss Result")
plt.show()      #gives pie chart of toss decision w.r.t Bat/Fielding first


# In[46]:


#obs 4
final=data1.drop_duplicates(subset=['season'], keep='last')
final[['season','winner']].reset_index(drop=True).sort_values('season')
        #gives the name of winner teams per season


# In[47]:


match = final.win_by.value_counts()
labels=np.array(Toss.index)
sizes = match.values
plt.figure(figsize = (8,5))
plt.pie(sizes, labels=labels,autopct='%1.1f%%',startangle=90)
plt.title('Match Result')
plt.show()           #gives pie chart of winning % in final match w.r.t match decision


# In[48]:


Toss=final.toss_decision.value_counts()
labels=np.array(Toss.index)
sizes = Toss.values
plt.figure(figsize = (8,5))
plt.pie(sizes, labels=labels,autopct='%1.1f%%',startangle=90)
plt.title('Toss Result')
plt.show()         #gives pie chart of winning % in final match w.r.t toss decision


# In[56]:


#obs 5
plt.figure(figsize = (8,5))
top= data1.player_of_match.value_counts()[:10]
top.plot.bar()
sns.barplot(x =top.index,y=top)
plt.show()      


# Above fig gives name of top plyaer in IPL.
# CH Gayle and AB de Villiers are the top players in match.

# In[57]:


#obs 5
final[['toss_winner','toss_decision','winner']].reset_index(drop=True)
  #gives the toss winner, toss decision and winner names in final match.


# In[58]:


#obs 6
final[['winner','player_of_match']].reset_index(drop=True)
  #gives the name for Man of the Match


# In[ ]:





# In[ ]:




