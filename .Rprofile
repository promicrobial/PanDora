options(max.print = 50, scipen = 999, width = 150, digits = 3,knitr.duplicate.label="allow")

if (any(stringr::str_detect(list.dirs(recursive = F), "renv"))) {
	suppressMessages(
		source("renv/activate.R")
	)
}

safe_library <- function(package_name) {
	if (requireNamespace(package_name, quietly = TRUE)) {
		suppressWarnings(suppressMessages(library(
			package_name,
			character.only = TRUE
		)))
		return(TRUE)
	} else {
		warning(
			paste(
				"Package",
				package_name,
				"is not installed. Some functions may not work properly."
			),
			call. = FALSE,
			immediate. = TRUE
		)
		return(FALSE)
	}
}

# List of required packages
required_packages <- c(
	"phyloseq",
	"tidyverse",
	"ggpubr",
	"RColorBrewer",
	"kableExtra",
	"vegan",
	"rstatix",
	"gtsummary",
	"gt",
	"conflicted"
)

# Load packages safely
loaded_packages <- sapply(required_packages, safe_library)

# Set up conflicts only if conflicted package loaded successfully
if (loaded_packages["conflicted"]) {
	tryCatch(
		{
			conflicted::conflicts_prefer(
				dplyr::filter,
				dplyr::select,
				dplyr::mutate,
				base::load,
				base::attr,
				stats::update,
				purrr::modify
			)
		},
		error = function(e) {
			warning("Could not set conflict preferences: ", e$message, call. = FALSE)
		}
	)
}

