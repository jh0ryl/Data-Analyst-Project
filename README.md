# Overview 

Welcome to my analysis of the data job market, which the primary focus in the Philippines. The goal of this project to understand the market of data-related job by examining the high-paying and in-demand skills that will lead to employment opportunities. 

The data sourced from [Luke Barousse's Python Course](https://huggingface.co/datasets/lukebarousse/data_jobs) which provides a foundation for my analysis, containing detailed information on job titles, salaries, locations, and essential skills. Through a series of Python scripts, the project highlights the most demanded skills, identifies high-paying technologies, and uncovers the optimal combination of demand and salary for aspiring data analysts.

# Tools I Used 

- **Python:** The main programming tools for the analysis
- **Pandas Library:** This was used to analyze the data.
- **Matplotlib Library:** I visualized the data.
- **Seaborn Library:** Helped me create more advanced visuals.
- **Jupyter Notebooks:** The tool I used to run my Python scripts which let me easily include my notes and analysis.
- **Visual Studio Code:** My main coding editor.
- **Git & GitHub:** For version control and sharing my Python code and analysis.

# Analysis

## 1. What are the most demanded skills for the top 3 most popular data roles in Philippines? 

To find the the most demanded skills for the top 3 most popular data roles, I created this visualization using Python and visualizing it with the help of Seaborn and matplotlib. 

### Results 

![Visualization of Top Skills Data Roles](images/skills_count.png) 

# Insights 

## The Data Industry in the Philippines Is Still Analyst-Heavy

The dominance of Excel and SQL suggests that many companies still operate at a traditional or intermediate analytics maturity level, where dashboards and reporting are the core responsibilities. 

- Excel and SQL remain the core foundation across data roles, showing that the Philippine job market is still heavily focused on traditional analytics and reporting, with both Business Analysts and Data Analysts relying on these skills the most, and SQL serving as the backbone of Data Engineering work.

- Visualization and communication tools (Tableau, Power BI, PowerPoint) are strongly demanded for analyst roles, highlighting the importance of turning data into clear insights for decision-making, whereas Data Engineering shifts focus toward technical implementation rather than presentation.

- Python, cloud platforms (Azure, AWS), and big data technologies like Spark are concentrated in Data Engineer roles, indicating a growing shift toward modern data infrastructure, automation, and scalable data pipelines as organizations evolve their data maturity. 

## 2. How are in-demand skills trending for Data Analyst? 

To find how skills are trending in 2025 for Data Analysts, I filtered data Analyst positions and grouped the skills by month of the job postings. The result shows the the top 5 skills of data analyst per month. 

### Results 

![Trending Top skills for Data Analyst in 2024](images\skills_trend.png)  

# Insights 

- Excel remains the most in-demand baseline skill, consistently leading all year and showing steady growth—meaning companies still expect analysts across all roles (junior, mid, senior) to be fluent in spreadsheet-based analysis.

- SQL shows strong, cyclical spikes, reflecting that data-heavy roles (data analysts, BI analysts, and operations analysts) lean heavily on database querying during peak reporting and project periods, making SQL a non-negotiable core technical skill.

- Python, Power BI, and Tableau form the “modern analytics stack”, with Python rising during technical project seasons and BI tools fluctuating but maintaining relevance—signaling that employers value analysts who can combine automation, visualization, and storytelling. 

## 3. How well do jobs and skills pay for Data Jobs in the Philippines?

Here you can see, I use boxplot to visualize the salary distribution of the top 6 data jobs with the most high paying salary throughout the year.   

### Results 

![Salary Distribution in the Philippines](images\salary_analysis.png)   

# Insights 

- Clear seniority-based progression: Across all roles shown, senior-level positions consistently earn significantly higher salaries, with Senior Data Engineers and Senior Data Analysts reaching well into the $110K–$130K range, showing strong career payoff for specialization and experience.

- Data Scientists and Engineers command the widest ranges: Data Scientists and Data Engineers show the broadest salary spreads, indicating high variance based on industry, company size, and technical depth—these roles have the highest earning ceilings, with Data Scientists reaching up to ~$160K.

- Business Analysts earn the lowest but most stable salaries: Compared to technical roles, Business Analysts have a much narrower and lower salary range (~$55K–$70K), showing less variability and emphasizing that technical and engineering-heavy roles offer greater long-term earning potential in the Philippines data field. 


## 4. Highest Paid & Most Demanded Skills for Data Jobs  

#### Visualize it 

```python
fig, ax = plt.subplots(2, 1)  

sns.set_theme(style='ticks')

# Top 10 Highest Paid Skills for Data Analysts
sns.barplot(data=df_DA_top_pay, x='median', y=df_DA_top_pay.index, hue='median', ax=ax[0], palette='dark:b_r')
ax[0].legend().remove()
ax[0].set_title('Top 5 Highest Paid Skills for Data Analysts')
ax[0].set_ylabel('')
ax[0].set_xlabel('')
ax[0].xaxis.set_major_formatter(plt.FuncFormatter(lambda x, _: f'${int(x/1000)}K'))


# Top 10 Most In-Demand Skills for Data Analystsr')
sns.barplot(data=df_DA_skills, x='median', y=df_DA_skills.index, hue='median', ax=ax[1], palette='light:b')
ax[1].legend().remove()
ax[1].set_title('Top 10 Most In-Demand Skills for Data Analysts')
ax[1].set_ylabel('')
ax[1].set_xlabel('Median Salary (USD)')
ax[1].set_xlim(ax[0].get_xlim())  # Set the same x-axis limits as the first plot
ax[1].xaxis.set_major_formatter(plt.FuncFormatter(lambda x, _: f'${int(x/1000)}K'))

plt.tight_layout()
plt.show()

```
### Results 

![Highest Paid & Most Demanded Skills for Data Jobs](images\highest_paid_skills.png)    

# Insights 

- High pay doesn’t always equal high demand: The highest-paid skills (BigQuery, Flow, Sheets, C, Zoom) are mostly niche or specialized tools, while the most in-demand skills (SQL, Tableau, Python, Excel) are foundational and widely required, showing a gap between market demand and salary premium.

- Core analytics stack remains dominant: SQL, Python, Tableau, and Excel top demand rankings—these are the pillars of daily analytics work. Employers consistently seek them because they directly drive reporting, automations, and decision support.

- Cloud & productivity ecosystems influence salary: High-paying skills are tied to cloud platforms (BigQuery), workflow automation (Flow), and enterprise tools (Zoom), suggesting companies reward analysts who operate within modern, integrated digital ecosystems rather than just traditional analytics tools.  


## 5. What is the most optimal skills for Data Analyst in the Philippines? 

To figure it out, i use scatter plott to to visualize the most high paying skills and also to see how many of those skills are in demand.  

### Results

![Most Optimal Skills for Data Analyst in the Philippines](images\optimal_skills.png)   

# Insights 

- SQL, Excel, Python, and Tableau offer the strongest balance between demand and salary, making them the most strategic core skills for Data Analysts — with SQL leading in job demand and consistently high compensation.

- Specialized tools like Jira, Snowflake, Looker, and PowerPoint command higher median salaries despite lower demand, suggesting that niche or technical competencies can significantly increase earning potential even if they appear less frequently in job postings.

- General office tools like Word and Power BI show lower salary influence, indicating that while they are commonly required, they contribute less to competitive advantage compared to analytical, programming, and data engineering–adjacent skills. 

## Overall Insights

- **Core analytical skills remain the backbone of the Philippine data job market**, with Excel and SQL consistently dominating both demand and usefulness across Business Analyst, Data Analyst, and even Data Engineer roles.

- **Advanced technical skills Python, cloud platforms, and big-data technologies drive higher salaries**, showing that specialization and technical depth significantly boost earning potential even though these skills appear less frequently in job postings.

- **The most strategic career path blends high-demand fundamentals with selective upskilling**, meaning analysts who master Excel/SQL and layer in Python, Tableau/Power BI, and cloud tools position themselves for both strong employability and long-term career growth.


