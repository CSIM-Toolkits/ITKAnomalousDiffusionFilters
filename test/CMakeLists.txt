itk_module_test()

set(AnomalousDiffusionFiltersTests
  itkMinimalStandardRandomVariateGeneratorTest.cxx
  itkNormalDistributionImageSourceTest.cxx
  itkAnisotropicAnomalousDiffusionImageFilterTest.cxx
  )

CreateTestDriver(AnomalousDiffusionFilters "${AnomalousDiffusionFilters-Test_LIBRARIES}" "${AnomalousDiffusionFiltersTests}")

itk_add_test(NAME itkMinimalStandardRandomVariateGeneratorTest
  COMMAND AnomalousDiffusionFiltersTestDriver itkMinimalStandardRandomVariateGeneratorTest
  )

itk_add_test(NAME itkAnisotropicAnomalousDiffusionImageFilterTest
  COMMAND AnomalousDiffusionFiltersTestDriver
    --compare
    ${ITK_TEST_OUTPUT_DIR}/itkAnisotropicAnomalousDiffusionImageFilterTestOutput.mha
    DATA{Baseline/itkAnisotropicAnomalousDiffusionImageFilterTestOutput.mha}
  itkAnisotropicAnomalousDiffusionImageFilterTest
    ${ITK_TEST_OUTPUT_DIR}/itkAnisotropicAnomalousDiffusionImageFilterTestOutput.mha
  )

itk_add_test(NAME itkNormalDistributionImageSourceTest
  COMMAND AnomalousDiffusionFiltersTestDriver --without-threads
  --compare
    ${ITK_TEST_OUTPUT_DIR}/itkNormalDistributionImageSourceTestOutput.mha
    DATA{Baseline/itkNormalDistributionImageSourceTestOutput.mha}
  itkNormalDistributionImageSourceTest
    ${ITK_TEST_OUTPUT_DIR}/itkNormalDistributionImageSourceTestOutput.mha
  )
