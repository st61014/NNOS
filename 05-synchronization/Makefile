# compiler / kompilátor
CC = gcc

# compiler switches / přepínače pro kompilátor
CFLAGS = -Wall -D_REENTRANT
# -Wall		warnings: all / vypisovat všechna varování
# -g		include debugging symbols / zahrnout symboly pro debugger
# -Dsymbol	define symbol like #define / definuje symbol jako #define
# -D_REENTRANT

# linker switches / přepínače pro linker
LDFLAGS =
# link libraries / knihovny pro linker
LDLIBS = -lpthread
# -llibrary / -lknihovna
#  libNAME.so.version	filename of the library / jméno souboru knihovny
# -lNAME
# e.g. / např.: -lpthread	link with libpthread.so / připojit knihovnu libpthread.so

# for semaphores and POSIX message queues / pro semafory a posixové fronty zpráv
%_sem %_semN %_msgPOSIX %_semPOSIX %_mqPOSIX: LDLIBS += -lrt

RM = /bin/rm -f

OBJECTS = *.o
BACKUPS = *~ *.bak
PROGRAMS = thread_add_barrier_mutex sync_barrier sync_cond_var sync_assignment producer_consumer \
	sync_working_threads_partial_sem # sync_working_threads_partial_mq_sem
INDIVIDUALLY = sync_sem sync_cond \
	producer_consumer_solved_sem \
	sync_working_threads_sem sync_working_threads_mq_sem

all: $(PROGRAMS)

solo: $(INDIVIDUALLY)

#target/cíl: dependencies (sources) / závislosti (zdrojové kódy)
#	commands to create target (program) / příkazy pro vytvoření cíle (programu)

test: sync_sem
	./$<

clean:
	@echo Deleting objects, backups and programs / Mažu objekty, zálohy a programy
	$(RM) $(OBJECTS) $(BACKUPS) $(PROGRAMS) $(INDIVIDUALLY)

