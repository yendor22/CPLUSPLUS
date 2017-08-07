TARGET = wk1rvw

CXX = g++
CFLAGS = -g -Wall -Werror -Wextra
# -g: adds debugging symbols in the binary
# -Wall: turn on various warning flags
# -Werror: error out on warnings
# -Wextra: turn on additional warning flags not enabled by -Wall

BINDIR = /usr/local/bin
OBJECTS = wk1rvw.o
SOURCES = wk1rvw.cpp

# Targets that do not represent actual files (but are just a label 
# representing a command script) should use special target .PHONY
# to avoid collision with an actual file (ie actual file named clean)  
# .PHONY tells make that this target is not a real file
.PHONY: all
.PHONY: clean
.PHONY: install
.PHONY: uninstall

all: $(TARGET)

clean:
	rm -f $(TARGET)
	rm -f $(OBJECTS)
#	rm -f $(BINDIR)/$(TARGET)

install: $(TARGET)
	cp $(TARGET) $(BINDIR)

uninstall:
	rm -f $(BINDIR)/$(TARGET)

$(TARGET): bld_msg $(OBJECTS)
	$(CXX) -o $(TARGET) $(OBJECTS)

$(OBJECTS): $(SOURCES)
	$(CXX) $(CFLAGS) -c $(SOURCES)

.PHONY: bld_msg
bld_msg:
	@printf "#\n# Building $(TARGET)\n#\n"

#SOURCES = 4_8.cpp
#OBJECTS = $(SOURCES:%.c=%.o)
#$(TARGET): $(OBJECTS)
#        $(CXX) -o $(TARGET) $^

#4_8.o: $(SOURCES)
#        $(CXX) $(CFLAGS) -c $^
