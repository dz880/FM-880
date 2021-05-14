# FM-880MIDIMessage: midi.MidiController = None
PressAB = False
PressC = False
PressB = False
PressA = False
RELEASEAB = False
RELEASEA = False
RELEASEB = False
RELEASEC = False
POT = 0
basic.show_icon(IconNames.QUARTER_NOTE)
controller1 = midi.channel(5)
controller2 = midi.channel(6)
controller3 = midi.channel(7)
midi.use_raw_serial()
serial.redirect(SerialPin.P0, SerialPin.P1, BaudRate.BAUD_RATE31250)

def on_forever():
    global PressA, PressB, PressC, PressAB, MIDIMessage, RELEASEC, RELEASEA, RELEASEB, RELEASEAB
    PressA = input.button_is_pressed(Button.A)
    PressB = input.button_is_pressed(Button.B)
    PressC = input.pin_is_pressed(TouchPin.P1)
    PressAB = input.button_is_pressed(Button.AB)
    if PressA and RELEASEA:
        controller1.control_change(0,
            Math.floor(abs(input.acceleration(Dimension.X) + 1024 / (2048 * 127))))
        basic.show_icon(IconNames.DIAMOND)
    else:
        pass
    if PressB and RELEASEB:
        MIDIMessage = midi.channel(1)
        MIDIMessage.note_on(69)
    else:
        if PressB and RELEASEB:
            MIDIMessage.note_off(69)
    if PressC and RELEASEC:
        MIDIMessage = midi.channel(3)
        MIDIMessage.note_on(67)
    else:
        if PressC and RELEASEC:
            MIDIMessage.note_off(67)
    if PressAB and RELEASEAB:
        MIDIMessage = midi.channel(4)
        MIDIMessage.note_on(70)
    else:
        if PressAB and RELEASEAB:
            MIDIMessage.note_off(70)
    RELEASEC = PressC
    RELEASEA = PressA
    RELEASEB = PressB
    RELEASEAB = PressAB
    basic.pause(100)
    if True:
        value = 0
        if value != POT:
            pass
    else:
        name = ""
        if name == "acy":
            pass
        else:
            if name == "acz":
                pass
basic.forever(on_forever)

MIDIMessage: midi.MidiController = None
PressAB = False
PressC = False
PressB = False
PressA = False
RELEASEAB = False
RELEASEA = False
RELEASEB = False
RELEASEC = False
POT = 0
basic.show_icon(IconNames.QUARTER_NOTE)
controller1 = midi.channel(5)
controller2 = midi.channel(6)
controller3 = midi.channel(7)
midi.use_raw_serial()
serial.redirect(SerialPin.P0, SerialPin.P1, BaudRate.BAUD_RATE31250)

def on_forever():
    global PressA, PressB, PressC, PressAB, MIDIMessage, RELEASEC, RELEASEA, RELEASEB, RELEASEAB
    PressA = input.button_is_pressed(Button.A)
    PressB = input.button_is_pressed(Button.B)
    PressC = input.pin_is_pressed(TouchPin.P1)
    PressAB = input.button_is_pressed(Button.AB)
    if PressA and RELEASEA:
        controller1.control_change(0,
            Math.floor(abs(input.acceleration(Dimension.X) + 1024 / (2048 * 127))))
        basic.show_icon(IconNames.DIAMOND)
    else:
        pass
    if PressB and RELEASEB:
        MIDIMessage = midi.channel(1)
        MIDIMessage.note_on(69)
    else:
        if PressB and RELEASEB:
            MIDIMessage.note_off(69)
    if PressC and RELEASEC:
        MIDIMessage = midi.channel(3)
        MIDIMessage.note_on(67)
    else:
        if PressC and RELEASEC:
            MIDIMessage.note_off(67)
    if PressAB and RELEASEAB:
        MIDIMessage = midi.channel(4)
        MIDIMessage.note_on(70)
    else:
        if PressAB and RELEASEAB:
            MIDIMessage.note_off(70)
    RELEASEC = PressC
    RELEASEA = PressA
    RELEASEB = PressB
    RELEASEAB = PressAB
    basic.pause(100)
    if True:
        value = 0
        if value != POT:
            pass
    else:
        name = ""
        if name == "acy":
            pass
        else:
            if name == "acz":
                pass
basic.forever(on_forever)
