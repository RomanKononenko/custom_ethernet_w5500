if (NOT PICO_NO_HARDWARE)
    add_subdirectory(spi_flash)
    add_subdirectory(mpu9250_spi)
    add_subdirectory(w5500_spi)
    add_subdirectory(bme280_spi)
    add_subdirectory(spi_dma)
endif ()


