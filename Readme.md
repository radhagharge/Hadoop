⚔️ 🧾 
HADOOP WORDCOUNT — COMPLETE FROM SCRATCH
🔹 STEP 0: Open terminal ( not needed always /ignore )
cd ~
source ~/.bashrc
🔹 STEP 1: Start Hadoop
start-dfs.sh
start-yarn.sh
🔹 STEP 2: Verify
jps
👉 Must show:

NameNode
DataNode
SecondaryNameNode
ResourceManager
NodeManager
🔹 STEP 3: Create working directory
mkdir 31125
cd 31125
🔹 STEP 4: Create input file
nano data.txt
Paste:

data science data analytics spark spark hadoop spark
Save:

Ctrl + O → Enter → Ctrl + X
🔹 STEP 5: Create Java file
nano WordCount.java
👉 Paste full WordCount code (your working one)

Save same way

🔹 STEP 6: Compile
javac -classpath `hadoop classpath` WordCount.java
🔹 STEP 7: Create JAR
jar cf WordCount.jar WordCount*.class
🔹 STEP 8: Clean previous HDFS run (IMPORTANT)
hdfs dfs -rm -r /31125
(ignore error if not exists)

🔹 STEP 9: Create HDFS directories
hdfs dfs -mkdir /31125
hdfs dfs -mkdir /31125/input
🔹 STEP 10: Upload file
hdfs dfs -put data.txt /31125/input
Check:

hdfs dfs -ls /31125/input
🔹 STEP 11: Run WordCount
hadoop jar WordCount.jar WordCount /31125/input /31125/output
🔹 STEP 12: View output
hdfs dfs -cat /31125/output/part-r-00000
🎯 EXPECTED OUTPUT
data 2
spark 3
hadoop 1
🔹 STEP 13 (optional): Stop Hadoop
stop-dfs.sh
stop-yarn.sh
💣 IMPORTANT RULES (DON’T FORGET)
❗ Never use 
/31125
for local folders
👉 Only for HDFS

❗ Always delete output before rerun
hdfs dfs -rm -r /31125
❗ Don’t work inside 
~/hadoop
🏆 FINAL MENTAL MODEL
Start Hadoop
Work in your folder
Upload to HDFS
Run job
View result
💀 Mentor verdict
Now you:
✔ can run Hadoop independently
✔ understand structure
✔ won’t panic in exam

If you want:
👉 I’ll give you exact viva answers for THIS execution flow (very high scoring)
