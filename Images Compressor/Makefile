SRC_DIR := src
OBJ_DIR := obj
BIN_DIR := bin

EXE := Quad
SRC := $(wildcard $(SRC_DIR)/*.c)
OBJ := $(SRC:$(SRC_DIR)/%.c=$(OBJ_DIR)/%.o)

CC=gcc
CFLAGS := -Wall -pedantic -lMLV -lm

.PHONY: all clean

all: $(EXE)

$(EXE): $(OBJ) | $(BIN_DIR)
	$(CC) $(SRC) -o $(EXE) $(CFLAGS)

$(OBJ_DIR)/%.o: $(SRC_DIR)/%.c | $(OBJ_DIR)
	$(CC) $(CFLAGS) -c $(SRC) 

$(BIN_DIR) $(OBJ_DIR):
	mkdir -p $@

clean:
	rm -f *.o
	rm -f Quad


-include $(OBJ:.o=.d)