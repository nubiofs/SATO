
prefix=/usr/local

libbase=${SATO_LIB_PATH}
incbase=${SATO_INC_PATH}

OPTFLAGS	= -O2
INCFLAGS	= -I $(incbase)
LIBS		= -lgeos -lspatialindex -L $(libbase)

CC = gcc
CXX = g++


all: resque skewresque skewresque2 containment

resque: resque.cpp tokenizer.h resquecommon.h
	$(CXX) $< $(INCFLAGS) $(LIBS) $(OPTFLAGS) -o $@

skewresque: skewresque.cpp tokenizer.h resquecommon.h
	$(CXX) -std=c++0x $< $(INCFLAGS) $(LIBS) $(OPTFLAGS) -o $@

skewresque2: skewresque2.cpp tokenizer.h resquecommon.h
	$(CXX) -std=c++0x $< $(INCFLAGS) $(LIBS) $(OPTFLAGS) -o $@

containment: containment.cpp tokenizer.h resquecommon.h
	$(CXX) -std=c++0x $< $(INCFLAGS) $(LIBS) $(OPTFLAGS) -o $@

install:
	mkdir -p $(prefix)/bin
	cp resque $(prefix)/bin
	cp skewresque $(prefix)/bin
	cp skewresque2 $(prefix)/bin
	cp containment $(prefix)/bin

clean:
	@rm -f resque skewresque skewresque2 containment

