CPPC = g++
LD = g++
CPPFLAGS = -O3 -g
LDFLAGS = -O3

DEPS_FILE = Makefile.deps
EXECUTABLE = imageParser
# format: yymmdd-cc; y-year, m-month, d-day, c-count
VERSION = 150430-01

MAIN_FILE = Mainfiles/$(EXECUTABLE).cpp

SRCS = Framework/Color.cpp Framework/Matrix2x2.cpp Framework/Transformation.cpp Framework/AbstractCanvas.cpp Framework/AbstractRasterCanvas.cpp Framework/QtImage.cpp Framework/QtRasterImage.cpp Framework/QtVectorImage.cpp Framework/MovieData.cpp \
Parser/LogCellNumber.cpp Parser/LogDualMarginDeformation.cpp Parser/Cell.cpp Parser/LogDualMarginState.cpp Parser/LogFile.cpp Parser/TissueState.cpp Parser/LogTriangleDeformation.cpp Parser/DeformingTissue.cpp Parser/LogTriangleState.cpp Parser/Triangle.cpp Parser/DirectedBond.cpp Parser/Vertex.cpp Parser/LogBondTriangleState.cpp Parser/Pixel.cpp Parser/LogCellNumberChange.cpp Parser/PixelFrame.cpp

ALL_SRCS = $(MAIN_FILE) $(SRCS) $(C_SRCS)

INCDIRS = -I/home/mmpi/include
# LIBDIRS = -L/home/mmpi/lib
DEFINES = -DPROGRAMNAME=\"$(EXECUTABLE)\" -DVERSION=\"$(VERSION)\" -DUSE_NETCDF
# DEFINES = -DPROGRAMNAME=\"$(EXECUTABLE)\"
INCDIRS = -IFramework -IParser -I/usr/include/qt4
LIBDIRS =
HEADERS = $(shell find . -name "*.h")
LIBS = -lnetcdf_c++ -lnetcdf -lQtGui -lQtCore -lm 
# LIBS = -lQtGui -lQtCore -lm
OBJS = Mainfiles/$(EXECUTABLE).o $(SRCS:.cpp=.o)

all: $(EXECUTABLE)

# Linkage
$(EXECUTABLE): $(OBJS)
	$(LD) $(LDFLAGS) $(LIBDIRS) $(OBJS) $(LIBS) -o $@

# Compilation
%.o: %.cpp
	${CPPC} $(CPPFLAGS) $(INCDIRS) $(DEFINES) -c -o $@ $<

# Dependencies
$(DEPS_FILE): Makefile $(ALL_SRCS)
	echo > $@
	makedepend -Y. -f $@ $(ALL_SRCS) $(INCDIRS) 2>makedeps.err
	rm -f makedeps.err $@.bak

# Cleaning:
clean:
	rm -f Framework/*.o Parser/*.o Mainfiles/*.o *.o
	rm -f Framework/*~ Parser/*~ Mainfiles/*~ *~
	rm -f $(DEPS_FILE)
	rm -f $(EXECUTABLE)
	rm -r archiveTemp
	
archive:
	mkdir -p archiveTemp archiveTemp/Framework archiveTemp/Parser archiveTemp/Mainfiles
	cp Makefile archiveTemp/
	cp Framework/*.h Framework/*.cpp archiveTemp/Framework/
	cp Parser/*.h Parser/*.cpp archiveTemp/Parser/
	cp Mainfiles/$(EXECUTABLE).cpp archiveTemp/Mainfiles/
	cd archiveTemp && tar cfz ../releases/imageParser_$(VERSION).tar.gz *
	rm -r archiveTemp

.PHONY: all clean deps

-include $(DEPS_FILE)