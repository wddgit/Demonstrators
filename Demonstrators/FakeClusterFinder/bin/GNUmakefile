# Include your header file location
CXXFLAGS += -I$(LARLITE_COREDIR)
CXXFLAGS += -I$(LARLITE_USERDEVDIR)/Demonstrators
CXXFLAGS += -I. $(shell root-config --cflags) -g

# Include your shared object lib location
LDFLAGS += -lDemonstrators_FakeClusterFinder
LDFLAGS += $(shell larlite-config --libs)
LDFLAGS += $(shell root-config --libs)

# platform-specific options
OSNAME = $(shell uname -s)
include $(LARLITE_BASEDIR)/Makefile/Makefile.${OSNAME}

# Add your program below with a space after the previous one.
# This makefile compiles all binaries specified below.
PROGRAMS = runClusterFinding

all:		$(PROGRAMS)

$(PROGRAMS):
	@echo '<<compiling' $@'>>'
	$(CXX) $@.cc -o $@ $(CXXFLAGS) $(LDFLAGS)
	@rm -rf *.dSYM
clean:	
	rm -f $(PROGRAMS)
