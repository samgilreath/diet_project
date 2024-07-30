# https://github.com/rdpeng/practice_assignment/blob/master/practice_assignment.rmd

# Download and unzip data
dataset_url <- "http://s3.amazonaws.com/practice_assignment/diet_data.zip"
download.file(dataset_url, "diet_data.zip")
unzip("diet_data.zip", exdir = "diet_data")

# store files with path appended
files <- list.files("diet_data", full.names=TRUE)

# create empty data frame
dat <- data.frame()

# add files to data frame
for (i in 1:5) {
        dat <- rbind(dat, read.csv(files_full[i]))
}

# median weight with NA removed
median(dat$Weight, na.rm=TRUE)