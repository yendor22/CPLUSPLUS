TARGET = helloworld

CXX = g++
CFLAGS = -g -Wall -Werror -Wextra
# -g: adds debugging symbols in the binary
# -Wall: turn on various warning flags
# -Werror: error out on warnings
# -Wextra: turn on additional warning flags not enabled by -Wall

BINDIR = /usr/local/bin

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
	rm -f hello.o
#	rm -f $(BINDIR)/$(TARGET)

install: $(TARGET)
	cp $(TARGET) $(BINDIR)

uninstall:
	rm -f $(BINDIR)/$(TARGET)

$(TARGET): bld_msg hello.o
	$(CXX) -o $(TARGET) hello.o

hello.o: hello.cpp
	$(CXX) $(CFLAGS) -c hello.cpp

.PHONY: bld_msg
bld_msg:
	@printf "#\n# Building $(TARGET)\n#\n"

#SOURCES = hello.cpp
#OBJECTS = $(SOURCES:%.c=%.o)
#$(TARGET): $(OBJECTS)
#        $(CXX) -o $(TARGET) $^

#hello.o: $(SOURCES)
#        $(CXX) $(CFLAGS) -c $^
