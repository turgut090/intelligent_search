
library(data.table)
library(magrittr)

my_csv_files = list.files(pattern = '.csv')
my_csv_list = list()

for(i in 1:length(my_csv_files)) {
  example = fread(my_csv_files[i],select = 'id')
  my_csv_list[[i]] <- example
  print(paste('Done',i,'out of',length(my_csv_files)))
  rm(example,i)
  gc()
}

df = rbindlist(my_csv_list)
rm(my_csv_list,my_csv_files)

num_of_dir = gsub('id_', '', list.dirs('imgs', F, F)) %>% 
  .[. %in% df$id]

#reticulate::py_install('--no-deps git+https://github.com/openai/CLIP.git',pip = T)


res=list.files('numpy/features',pattern = '.csv',full.names = T)

data.table::fread(res[1])









