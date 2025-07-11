SRC_DIR = src
BIN_DIR = bin
INC_DIR = include
DATA_DIR = data

CC = gcc
CFLAGS = -I$(INC_DIR) -Wall -Wextra

SRCS = $(wildcard $(SRC_DIR)/*.c)
OBJS = $(patsubst $(SRC_DIR)/%.c, $(BIN_DIR)/%.o, $(SRCS))

EXEC = core

all: $(EXEC)

$(EXEC): $(OBJS)
	$(CC) -o $@ $^ -lm


$(BIN_DIR)/%.o: $(SRC_DIR)/%.c
	@mkdir -p $(BIN_DIR)
	$(CC) $(CFLAGS) -c $< -o $@

clean:
	rm -f $(BIN_DIR)/*.o $(EXEC)

clean-all: clean
	rm -f $(DATA_DIR)/pedidos.dat

run: all
	./$(EXEC)

.PHONY: all clean clean-all run