# GatkTutoring
//To seek the infomation of a given sequence (.bam file)
[root@localhost GATK_softwares]# $SAMTOOLS view -h /home/liangxinwen/GATK_softwares/helloHaplotypeCaller/inputs/NA12878_wgs_20.bam | grep '@RG'
@RG     ID:H0164.2      PL:illumina     PU:H0164ALXX140820.2    LB:Solexa-272222PI:0    DT:2014-08-20T00:00:00-0400     SM:NA12878      CN:BI

[root@localhost GATK_softwares]# $SAMTOOLS view -h /home/liangxinwen/GATK_softwares/helloHaplotypeCaller/inputs/NA12878_wgs_20.bam | grep '@RG'
 //which will show the processing steps before you get the file.
 
 [root@localhost GATK_softwares]# java -jar $PICARD ValidateSamFile \ I=/home/liangxinwen/GATK_softwares/helloHaplotypeCaller/inputs/NA12878_wgs_20.bam \
MODE=SUMMARY
//To check the quality

[root@localhost GATK_softwares]# GenomeAnalysisTK -T HaplotypeCaller \
    -R ref/human_g1k_b37_20.fasta \
    -I bams/exp_design/NA12878_wgs_20.bam \
    -o sandbox/NA12878_wgs_20_HC_calls.vcf \
    -L 20:10,000,000-10,200,000
    //To call SNP
    
