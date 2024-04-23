OBJDIR=obj
LIBDIR=../lib
INCDIR=../include
OUTDIR=../output

CXX=g++
CXXFLAGS=-I$(INCDIR) -I/usr/local/include -Wall -std=c++20

LIBS = -L/usr/local/lib -lSDL2 -Wl,-rpath=/usr/local/lib

ifdef DEF
USEDEF=-D $(DEF)
else
USEDEF=
endif

_DEPS=
DEPS=$(patsubst %,$(INCDIR)/%,$(_DEPS))

_OBJ=main.o
OBJ=$(patsubst %,$(OBJDIR)/%,$(_OBJ))

EXE=jpegEditor

all: $(EXE)

$(OBJDIR)/%.o: %.cpp $(DEPS)
	$(CXX) -c -o $@ $< $(CXXFLAGS) $(USEDEF)

$(EXE): $(OBJ)
	$(CXX) -o $(OUTDIR)/$@ $^ $(CXXFLAGS) $(LIBS) $(USEDEF)

.PHONY: clean

clean:
	rm -f $(OBJDIR)/*.o *~ core $(INCDIR)/*~
