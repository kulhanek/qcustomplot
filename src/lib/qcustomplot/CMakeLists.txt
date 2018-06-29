# ==============================================================================
# QCustomPlot CMake File
# ==============================================================================

SET(QCUSTOMPLOT_LIB_SRC
        qcustomplot.cpp
        )

# create shared library --------------------------------------------------------

ADD_LIBRARY(qcp_shared SHARED ${QCUSTOMPLOT_LIB_SRC})

TARGET_LINK_LIBRARIES(qcp_shared ${SYSTEM_LIBS})

QT5_USE_MODULES(qcp_shared Core Widgets Gui)

SET_TARGET_PROPERTIES(qcp_shared PROPERTIES
                        OUTPUT_NAME ${QCP_LIB_NAME}
                        CLEAN_DIRECT_OUTPUT 1
                        VERSION ${QCP_VERSION})
INSTALL(TARGETS
            qcp_shared
        DESTINATION
            lib
        )

#-------------------------------------------------------------------------------
