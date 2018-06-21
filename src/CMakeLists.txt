set(AnomalousDiffusionFilters_SRCS
  itkMinimalStandardRandomVariateGenerator.cxx
  )

itk_module_add_library(AnomalousDiffusionFilters ${AnomalousDiffusionFilters_SRCS})
