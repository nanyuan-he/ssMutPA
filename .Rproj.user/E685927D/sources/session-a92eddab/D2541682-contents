#' @title Converts MAF file or data in other formats into mutation matrix.
#' @description The function `get_mut_status` is used to convert MAF file or data in other formats into a binary mutation matrix.
#' @param maf_data The patients' somatic mutation data, which in MAF format or others.
#' @param nonsynonymous Logical. Determine if extract the non-silent somatic mutations .
#' @param TCGA Logical. Determine whether the file is in MAF format .
#' @param mut_rate Used to filter genes with target mutation rate .
#' @importFrom utils read.delim
#' @return A binary mutations matrix, in which 1 represents that a particular gene has mutated in a particular sample, and 0 represents that gene is wild type.
#' @export
#' @examples
#' #load the data
#' mut_path <- system.file("extdata","mutation_data.Rdata",package = "ssMutPA")
#' load(mut_path)
#' #perform the function `get_mut_status`.
#' mut_status<-get_mut_status(mutation_data,nonsynonymous=TRUE,TCGA=TRUE,mut_rate=0)

get_mut_status<-function(maf_data,nonsynonymous = TRUE,TCGA = TRUE,mut_rate = 0){
  if(TCGA){
    mutvariant<-maf_data[,c("Hugo_Symbol",
                            "Tumor_Sample_Barcode",
                            "Variant_Classification")]
    if(nonsynonymous){
      mafmut<-mutvariant[which(
        mutvariant$Variant_Classification == "Missense_Mutation" |
          mutvariant$Variant_Classification == "Frame_Shift_Del" |
          mutvariant$Variant_Classification == "Frame_Shift_Ins" |
          mutvariant$Variant_Classification == "In_Frame_Del" |
          mutvariant$Variant_Classification == "Nonsense_Mutation" |
          mutvariant$Variant_Classification == "In_Frame_Ins" |
          mutvariant$Variant_Classification == "Splice_Site" |
          mutvariant$Variant_Classification == "Nonstop_Mutation" |
          mutvariant$Variant_Classification == "Translation_Start_Site"
      ),]
    }else{
      mafmut<-mutvariant
    }
  }else{
    mutvariant<-maf_data[,c("gene",
                            "Sample_ID",
                            "effect")]
    if(nonsynonymous)
    {
      mafmut<-mutvariant[which(
        mutvariant$effect == "missense_variant" |
          mutvariant$effect == "frameshift_variant" |
          mutvariant$effect == "stop_gained" |
          mutvariant$effect == "stop_lost" |
          mutvariant$effect == "5_prime_UTR_variant" |
          mutvariant$effect == "inframe_deletion" |
          mutvariant$effect == "inframe_insertion" |
          mutvariant$effect == "splice_region_variant" |
          mutvariant$effect == "splice_acceptor_variant" |
          mutvariant$effect == "splice_donor_variant"
      ),]
    }else {
      mafmut<-mutvariant
    }
  }
  mut_status<-matrix(data=0,nrow=length(unique(mafmut[,1])),ncol=length(unique(mafmut[,2])))
  colnames(mut_status)<-unique(mafmut[,2])
  rownames(mut_status)<-unique(mafmut[,1])
  for(i in 1:dim(mut_status)[2]){
    un_sname<-table(mafmut[which(mafmut[,2]%in%colnames(mut_status)[i]),1])
    mut_status[match(names(un_sname),rownames(mut_status)),i]<-un_sname
  }
  mut_status[mut_status>1]<-1
  a<-apply(mut_status, 1,function(x){length(which(x!=0))/length(x)})
  mut_status<-mut_status[a > mut_rate,]
  return(mut_status)
}
