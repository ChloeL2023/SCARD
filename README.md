# SCARD

Preparation:
1. CRAM file and index file (i.e sample.cram stored in $dir = $PATH_TO_WORKING_DIRECTORY) #recommended to work in a dir named after your sample
2. mkdir -r $PATH_TO_WORKING_DIRECTORY/ID/SCARD
3. bin folder in $PATH_TO_WORKING_DIRECTORY/bin/

# For proband analysis:
$PATH_TO_WORKING_DIRECTORY/bin/write.SCARD.single $SAMPLE_ID $PATH_TO_WORKING_DIRECTORY $PATH_TO_CRAM

Example: /path/for/anlaysis/bin/write.SCARD.single NA12878 /path/for/anlaysis /path/for/anlaysis/NA12878/NA12878.cram

# For trio analysis:
#Run it after proband analysis for every member.
$PATH_TO_WORKING_DIRECTORY/bin/write.SCARD.trio $PATH_TO_FETUS_SCARD_RESULT $PATH_TO_MOTHER_SCARD_RESULT $PATH_TO_FATHER_SCARD_RESULT $PATH_TO_FETUS_CRAM_OR_BAM $PATH_TO_MOTHER_CRAM_OR_BAM $PATH_TO_FATHER_CRAM_OR_BAM $PATH_TO_FETUS $FETUS_ID $PATH_TO_WORKING_DIRECTORY > run.sh

Example: fetus-HG00405, mother-HG00404, father-HG00403
/path/for/anlaysis/bin/write.SCARD.trio /path/for/anlaysis/HG00405/SCARD /path/for/anlaysis/HG00404/SCARD /path/for/anlaysis/HG00403/SCARD /path/for/anlaysis/HG00405/HG00405.cram path/for/anlaysis/HG00404/HG00404.cram path/for/anlaysis/HG00403/HG00403.cram path/for/anlaysis/HG00405 HG00405 /path/for/anlaysis > run.sh 
nohup sh run.sh 1>run.sh.o 2>run.sh.e &
