# Makefile for 'espeakedit' program

SRCS= compiledata.cpp compiledict.cpp debug.cpp dictionary.cpp espeak_command.cpp \
    espeakedit.cpp event.cpp extras.cpp fifo.cpp formantdlg.cpp intonation.cpp \
    klatt.cpp mbrowrap.cpp menus.cpp numbers.cpp options.cpp phonemelist.cpp \
    prosodydisplay.cpp readclause.cpp setlengths.cpp speak_lib.cpp spect.cpp \
    spectdisplay.cpp spectseq.cpp synthdata.cpp synthesize.cpp synth_mbrola.cpp \
    translate.cpp transldlg.cpp tr_languages.cpp voicedlg.cpp voices.cpp vowelchart.cpp \
    wave.cpp wavegen.cpp sonic.cpp

OBJS=$(patsubst %.cpp,%.o,$(SRCS))

WX_LIBS = -pthread   -lwx_gtk2u_xrc-2.6 -lwx_gtk2u_qa-2.6 -lwx_gtk2u_html-2.6 \
   -lwx_gtk2u_adv-2.6 -lwx_gtk2u_core-2.6 -lwx_baseu_xml-2.6 -lwx_baseu_net-2.6 -lwx_baseu-2.6

LIBS=-lstdc++ -lportaudio

CPPFLAGS =  -Wall -g -fexceptions -I/usr/lib/wx/include/gtk2-unicode-release-2.6
	-I/usr/include/wx-2.6 \
	-DGTK_NO_CHECK_CASTS -D__WXGTK__ -D_FILE_OFFSET_BITS=64 -D_LARGE_FILES
	-D_LARGEFILE_SOURCE=1 -DNO_GCC_PRAGMA -D_ESPEAKEDIT

CXXFLAGS = -O2  -Wall -fexceptions -I/usr/lib/wx/include/gtk2-unicode-release-2.6 -I/usr/include/wx-2.6 \
   -DGTK_NO_CHECK_CASTS -D__WXGTK__ -D_FILE_OFFSET_BITS=64 -D_LARGE_FILES -D_LARGEFILE_SOURCE=1 -DNO_GCC_PRAGMA -D_ESPEAKEDIT

all: espeakedit

.cpp.o:
	$(CXX) $(CXXFLAGS) -I. -c -fno-exceptions $<

espeakedit: $(OBJS)
	$(CXX) -o $@ $(OBJS) $(LIBS) $(WX_LIBS)

clean:
	rm -f *.o *~

distclean: clean
	rm -f espeakedit

