# Docker inheritance
FROM ycheng2022/bioconductor_docker_workflow_cellxgene_h5ad:devel
ENV knitr_eval FALSE
ENV fileId "e2874fd9-af11-4adf-a47a-f380b7606434"
ENV sample "Name"
ENV mem_gb 240

# install Rcollectl with the vignette
COPY install_Rcollectl.R /tmp/install_Rcollectl.R
COPY run_Rcollectl.R /tmp/run_Rcollectl.R

RUN chmod +x /tmp/install_Rcollectl.R
RUN chmod +x /tmp/run_Rcollectl.R

RUN /tmp/install_Rcollectl.R

WORKDIR /output

CMD /tmp/run_Rcollectl.R $knitr_eval $fileId $sample $mem_gb
