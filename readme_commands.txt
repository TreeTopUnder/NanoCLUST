

export TOWER_ACCESS_TOKEN=4b252dc4118da98eaaacebd6e07aa6670f000934
export NXF_VER=22.04.2

nextflow run main.nf -profile test,docker -dsl1

nextflow run main.nf -profile test,awsbatch -dsl1 \
  --awsqueue NextFlow_Queue_1 --awsregion eu-west-1  \
 -bucket-dir 's3://microbialgenomics-scratch/'  --tracedir /tmp/tracedir\
 -w 's3://microbialgenomics-scratch/' --outdir  's3://microbialgenomics-scratch/results' -with-tower