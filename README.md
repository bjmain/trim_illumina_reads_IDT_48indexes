# trim_illumina_reads_IDT_48indexes

mkdir trimmed

for file in *1.fastq.gz
do
java -jar /usr/local/Trimmomatic/trimmomatic-0.30.jar SE -threads 8 -phred33 $file trimmed/$(basename $file .fastq.gz).qc.fastq.gz ILLUMINACLIP:IDT48plex.fa:2:30:10 LEADING:3 TRAILING:3 SLIDINGWINDOW:4:15 MINLEN:36
done


