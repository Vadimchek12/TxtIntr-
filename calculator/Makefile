.PHONY: all debug release clean

RELEASE_FLAGS = -O2 -Wall -DNDEBUG
DEBUG_FLAGS   = -g -O0 -Wall
RELEASE_EXEC  = task_1
DEBUG_EXEC    = task_1-dbg
SOURCE        = task_1.cpp

all: debug release

debug: $(DEBUG_EXEC)

$(DEBUG_EXEC): task_1.cpp
	g++ $(DEBUG_FLAGS) task_1 -o $(DEBUG_EXEC) 

release: $(RELEASE_EXEC)

$(RELEASE_EXEC): task_1.cpp
	g++ $(RELEASE_FLAGS) task_1.cpp -o $(RELEASE_EXEC)

clean:
	rm -f $(RELEASE_EXEC) $(DEBUG_EXEC)
