Version v2014-11-04 =======================================================

Changes:
- fixed handling of favorites for Samsung F and H series
- fixed deleting of channels for older LG models (LD,LE,LH)

The complete change log can be found at the end of this document


About ChanSort ============================================================

ChanSort is a program to manage your Samsung, LG, Toshiba or Panasonic TV's
channel list on your PC.

It allows you to change program numbers and channel names, select your 
favorites, set a parental lock and much more. With its multi-selection 
capabilities and the side-by-side view of your sorted list and the available
channels a list can be created in no-time.

You can apply reference lists to your TV data file to restore a previous 
order, e.g. after running a channel scan. You can even apply the same 
reference list to TVs from different manufacturers.

You can get get the latest version and support on  
http://sourceforge.net/p/chansort/discussion/ or by contacting me by email:
mailto:horst@beham.biz


! USE AT YOUR OWN RISK !
------------------------
This software was written without access to official documentation about 
the file formats involved. Without full knowledge about the specifics of a
format there is a chance of unwanted side-effects or damage to your TV.


Supported TV models =======================================================

Samsung 
-------
    Series: B (2009)*, B (2013), C, D, E, F, H
    Lists:  Air analog, Air digital, Cable analog, Cable digital, 
            Cable Prime, Sat digital, Astra HD+, Freesat, TivuSat,
            Canal Digital Sat, Digital+, Cyfra+

    * NOTE: The "clone.bin" format is not supported. In the "*.scm" format
    the "Air Analog"-list of the 2009 B-series doesn't support all 
    editing features due to a lack of test files. If you have such a file,
    please send it to me.

    Instructions for transferring the channel list can be found on:
    http://www.ullrich.es/job/sendersortierung/senderlisten-samsung-tv-exportieren-importieren/

LG
------
    Series: CS, DM, LA, LB, LD, LE, LH, LK, LM*, LN, LP**, LS, LT, LV, LW,
            LX, PM, PN, PT
    Lists:  Analog TV, DTV (DVB-C, DVB-T), Radio (DVB-C/T), 
            Sat-DTV (DVB-S2), Sat-Radio (DVB-S2)
  
    * NOTE: See system requirements for LM-series.
            Model xxLM640T is not supported due to its broken firmware.
    **:     Only satellite channels supported
    Other models might also work, but have not been tested. If you have a
    .TLL file of a series not listed here, please send it to me.
    
    Instructions on how to access the hidden service-menu for transferring
    the channel list from/to USB can be found here:
    http://sourceforge.net/p/chansort/wiki/Home/

Panasonic
-------
    Viera models with an svl.bin or svl.db channel list
    (most/all? models since 2011)

Toshiba
-------
    Models that export a .zip file containing chmgt.db, dvbSysData.db and
    dvbMainData.db files.
    (e.g. RL, SL, TL, UL, VL, WL, XL, YL models of series 8xx/9xx)

VDR (Linux Video Disk Recorder)
-------
    Supports the channels.conf file format.
    Implementation for this was provided by TCr82 from the VDR project.

System requirements =======================================================

- Microsoft .NET Framework 4.0 (Full): included in Win8, can be installed
  manually on Windows 7, Windows Vista and Windows XP SP3
  http://www.microsoft.com/en-us/download/details.aspx?id=17851
- Microsoft Visual C++ 2010 Redistributable Package (x86)
  Required to edit Panasonic and Toshiba channel lists (through SQLite)
  http://www.microsoft.com/en-us/download/details.aspx?id=8328
- USB-stick to transfer the channel list between your TV and PC
  (for Panasonic an SD-Card is needed instead of a USB-stick)
- For some LG series/models the included remote control is not able to open
  the service menus for transferring the lists to/from USB.
  In that case you either need a different LG or a programmable remote. 
  (e.g. Logitech Harmony 300, One-For-All URC3920,...)
  Details can be found on the ChanSort wiki and on 
  http://openlgtv.org.ru/wiki/index.php/Access_hidden_service_menus_/_modes


License ===============================================================

GNU General Public Licence, Version 3: http://www.gnu.org/licenses/gpl.html
Source code available on http://sourceforge.net/projects/chansort/

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.

IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR
OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE,
ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.


Change log ================================================================

2014-11-04
- fixed handling of favorites for Samsung F and H series
- fixed deleting of channels for older LG models (LD,LE,LH)

2014-11-02
- fixed reading Samsung channel lists containing empty satellite records
- disabled individual sorting of favorite lists for Samsung F and H series.
  It appears that only the E series firmware supports this feature.
- disabled deleting of channels from LG's GlobalClone channel lists because
  the TV does not support this. Instead they are appended at the end of the
  list.
- added support for Samsung "map-AirCableMixedA" and "map-AirCableMixedD"
  channel lists (used by some hospitality TVs)
- disabled editing of channel names for Panasonic lists to prevent side
  effects after saving (e.g. incorrect alphabetical sorting shown on TV)

2014-09-11
- fixed support for LG LV/LW DVB-C/T channel lists
- added support for Samsung map-CyfraPlusD channel list
- added Russian translation (thanks to some anonymous developer!)

2014-07-14
- fixed issue with broken channel lists for LG models LV, 
  LW (except LW4500, LW5400), LK950S and PM670S
- added support for LG's LY series binary TLL file format

2014-07-11
- improved accessibility support (channel list and prog/fav list selection)

2014-07-08
- added Accessibility menu and hotkeys to directly select the input source
  (Alt+1 to Alt+9) and the program/favorite lists (Ctrl+Alt+0, ...)
- addes support for LG LH250C

2014-06-10
- fixed problem with incorrect favorites when applying a reference list
- added function "Edit / Renumber Favorites by Pr#" to use the same numbers
  in all lists

2014-06-08.3
- fixed problem with Toshiba lists that refer to invalid satellites

2014-06-08.2
- added support for LG xxLB580V analog and DVB-C/T channel lists

2014-06-08
- fixed loading of Panasonic svl.db / svl.bin files

2014-05-30
- fixed issues with LG "GlobalClone" XML file format

2014-05-29
- supports LG LB55xx and LB56xx xxLB*.TLL channel lists 
- supports LG LB58xx*.TLL channel lists
  (satellite channels ONLY due to lack of DVB-C/T test files)
- supports LG *Clone*.TLL channel lists (e.g. LA8xxx, LB6xxx, LB7xxx models)
  (deleting channels is not yet implemented)

2014-05-06
- Added support for Canal+ Digital channel list (map-DigitalPlusD)
- Fixed: "Save reference file" ignored the entered filename for .csv lists
- Improved file format detection for Freesat, Tivusat, Canal Digital Sat

2014-05-05
- Added support for VDR *.conf channel list format 
  (Thanks to TCr82 for providing this code patch!) 

2014-01-27
- Added support for Samsung "Channel Digital Sat" channel lists

2014-01-21
- show channel "Provider" information for Samsung C,D and E series DVB-C/T 
  and Satellite channel lists (no data available for Astra HD+)

2013-12-22
- Analog channel names loaded from a reference file (.csv, .csm, .tll, ...)
  are now copied into and saved with the current TV data file .

2013-12-20
- fixed incorrect disabling of "move channel up" button/menu item

2013-12-19
- Support for Samsung Tivusat channel list

2013-12-15
- Support for new channel list file format introduced by LG's firmware
  04.20.29 for LA- and LN-series
- LG DVB-C/T channel numbers are now marked as "moved" so that the TV
  does not change them automatically

2013-11-24
- Load and repair corrupted Panasonic and Toshiba SQLite channel lists

2013-11-23
- Channel lists can now be printed
- Fix: Error when saving Toshiba and Panasonic channel list which contained
  red proxy entries for missing channels after applying a reference list
- Fix: Modified Panasonic channel names were not written to the file

2013-11-20
- Panasonic: Handling of special characters in channel names
- Toshiba: channels didn't change their order for zapping in .zip/chmgt.db 
  channel lists (thanks to Kurt W. for the hint)

2013-11-16
- FIX: changes to Samsung channel lists after the first "save file" 
  operation were lost. Only the first save operation worked as expected.
- FIX: channels in Samsung B-series DVB-C/T channel lists were incorrectly
  identified and marked as deleted/active, resulting in duplicate program
  numbers on the TV.
- FIX: channel names in Samsung lists sometimes showed "..." after the end
- FIX: dragging something (e.g. a file) from outside ChanSort over one of
  its tables causes an error

2013-11-12 (beta)
- Experimental support for modifying LG channel lists with predefined
  channel numbers (LCN)
- Backed-out some changes from 2013-11-09 which may have caused incorrect
  handling of deleted channels in Samsung channel lists

2013-11-09
- File / "File information" now shows information for all TV models
- Disabled "TV-Set" menu items which are not applicable
- Fixed DVB-S transponder/frequency information for LG LN and LA61xx series
- Fixed deleting channels in Samsung B-series Digital Air/Cable lists
- Fixed encryption information in Samsung B-series Digital Air/Cable lists
- Fixed loading of reference lists with non-unique channel identifiers
- Fixed error when saving LG files for models LD-LK after applying a
  reference list which contains channels not present in the TLL file

2013-10-23
- Support for Samsung's Monitor/TV 3-series (LTxxy3)

2013-10-22
- Support for Samsung's 2013 B-Series

2013-10-07
- Added support for Samsung "FreesatD" channel lists
- Added support for LG LP-series sat channel lists (DVB-C/T not supported)
- Added columns for "skip" and "hide" channel flags to left list
- skipped/hidden channels are now display with blue/light grey color
- LG hotel-mode/DTV-update settings editable for all supported LG models

2013-09-15
- Added support for LG PN-series satellite channel lists
- Fixed: use last selected character set when loading LG channel lists
- Fixed missing translations

2013-08-21
- Added support for LG PN-series (tested with PN6500)

2013-08-19
- Fixed loading Samsung B-series channel lists
- Changed file filter for LG to "xx*.TLL" to exclude the GlobalClone*.TLL
  files of LA and LN series.
- Fixed "New version available" info screen
- Improved error handling

2013-07-23
- Added support for LG LT-series (tested with xxLT380H)

2013-07-22
- Display message box to install VC++ 2010 Redist Package (x86) when it is
  missing (required by SQLite to load Panasonic and Toshiba lists)
- FIX: added missing files for Portuguese translation

2013-07-19.3
- FIX: .NET Framework 4.0 exceptions about loading DLLs downloaded from
  the web (since the whole .zip was downloaded from the web)

2013-07-19.2
- FIX: Samsung "CablePrime" channel list was not updated/saved
- FIX: Deleted Samsung analog, DVB-T and DVB-C channels re-appeared in the
  channel list after loading the file again.

2013-07-19
- Supports Panasonic "svl.bin" channel lists for different TV CPUs
  (auto-detecting big-endian or little-endian byte order).
- *.csv reference list is no longer created automatically. (You can always
  use your TV data file as a reference list anyway)
- File / Save reference list... now opens a dialog which allows to save in
  either ChanSort *.csv or SamToolBox *.chl format.
  (The *.chl format only contains the currently selected list, so it can be
  used to duplicate the order from e.g. the "Astra HD+" to the "Satellite"
  list within the same *.scm file)
- Upgraded to .NET Framework 4.0  and DevExpress 13.1 libraries

2013-07-03
- Support for individually sorted favorite lists, if supported by TV
  (e.g. Samsung E and F series, Panasonic Viera)
- FIX: "insert after" using drag and drop from right to left list 
  inserted before instead of after the drop position

2013-07-02
- FIX: wrong version number (caused a popup about a newer version online)

2013-07-01
- Added support for Panasonic channel list (svl.db and svl.bin format)
- Translated UI to Portuguese (Thanks to Vitor Martins Augusto)

2013-06-24
- FIX: Resizing a column caused an exception
- FIX: Deleting satellite channels from an SCM file did not work correctly
- Improved SCM file format detection
- Samsung E/F-series: channels in the favorite lists now use their prog#
  instead of all being put at #1 
  (in a future version the fav lists may be sorted separately)

2013-06-23
- Drag&Drop inside left list and from right to left list 
  (only available when the left list is sorted by "New Pr#")
- Simplified menu/tool bar
- FIX: Moving multiple channels down now works correctly
- FIX: +/- keys no longer open the cell-editor after moving a channel
- Editor for "New Pr#" no longer opens when pressing non-numeric keys
- Move up/down is now disabled when left list is not sorted by "New Pr#"

2013-06-22
- Showing separate DVB-C and DVB-T lists for LG TVs (LA series can have
  both lists while prior models only had one)
- FIX: Lists for LG's LD,LE,LX,PK (except 950), PT, LW4500, LW5400 models
  are now physically reordered
- Empty lists are no longer displayed

2013-05-29
- Added support for Samsung "CablePrime" channel lists
- FIX: error when loading a Samsung files which only contains an 
  AstraHDPlus channel list.
- Channel name editor now limits the input to the maximum number of 
  characters allowed by the file format (e.g. 5 chars for Samsung analog
  channel names)

2013-05-16
- FIX: on LG's LA and LN models the DVB-S symbol rate got corrupted
- disabled editing of LG channel lists whith preset program numbers
- last file is no longer loaded automatically when starting ChanSort

2013-05-11
- TV data files can be used as reference lists (without exporting .csv)
- added "File / Export Excel list" function
- added hotkeys to many menu items
- added most recently used files to menu
- added support to enable Hotel Mode for LH3000 and LN models
- fixed: saved incorrect DVB-S transponder symbol rate for LG's LK950S, LV,
  LW and LN models
- re-added "TV-Set / Clean channel data" function for LG TV's.


2013-05-07
- Added support for LG's LN-series
- Fixed: Saving reordered list for LG xxLH3000.
- Removed "Cleanup TV data file" function which bricked one LG TV.

2013-05-03
- Added Assistants for loading and saving files
- Added support for LG's 2013 LA-series DVB-S channel lists.
  Due to a lack of test files containing analog or DVB-C/T channels, these
  lists are not supported yet. If you have a TLL file with such channels 
  please send it to horst@beham.biz.
- Added support for LG's LH3000 Model
- Improved clean-up of LG channel lists. This should solve problems with
  program numbers changing randomly or inability to change them at all.
- Fixed: Program number and channel name can be edited again by directly 
  typing the number or name on the keyboard.
- Fixed: Sorting and column layout is now preserved when switching lists
- Fixed: Missing channels from a reference list appeared as valid channels
  in the UI after saving a TLL file.

2013-04-21
- Fix: Encryption flag for Samsung analog and DVB-C/T lists now shown 
  correctly
- Added "Remove channels" function to right list. E.g. you can use this to
  search and select encrypted channels in the right list and remove them 
  (from the sorted list).
- Text editor for channel number or name now only opens after holding the
  left mouse button down for at least 0.5sec. This prevents it from opening 
  when you double-click a channel.
- Added "Edit channel name" function to menus (due to the editor no longer
  opening automatically after a short click on the name)
- Warnings and information about TV file content are no longer shown when
  opening the file. It can be viewed by using the 
  "File / Show file information" menu item.
- Added experimental loader for Panasonic TV files. 
  Saving is not supported yet!

2013-04-11
- added support for Toshiba *.zip channel lists (containing chmgt.db list)
- allow Pr #0 for analog channels
- FIX: first channel list only got populated after switching between tabs

2013-04-08
- Added support for Samsung F-series.
- Added online check for updated program version

2013-04-07
- FIX: saving a .TLL file after loading a reference list which contained 
  channels that are no longer inside the .TLL caused an error during saving

2013-04-06
- FIX: When double-clicking a channel in the right list, which was already 
  part of the sorted list, the wrong channel was selected in the left list.
- new application icon which is licensed free-to-use

2013-04-05
- Redesigned user interface
- Editing option to close or keep gaps when moving/deleting channels
- Support for LG LMxxxT models, which export an invalid DVB-S data block
- Opening a file automatically shows the first non-empty channel list
- Reloading a TV-file will show the last opened list
- FIX: Deleting rows caused incorrect selections in the left list. 
  Successive deletes resulted in the loss of the first channel.
- FIX: Duplicate Pr# was assigned to channels when they were added out of
  order

2013-04-04
- Deleting channels for Samsung TVs now stores the files correctly 
  (no longer showing them all on Pr #0 on your TV)

2013-04-03 (major release)
- complete re-write of the code for loading/saving TV-data files (SCM, TLL)
  and reference lists (CSV).
- added support for LG's LX-models
- channel names can now be edited for both LG and Samsung 
- menu item for (un-)setting favorite #5 for Samsung series E
- Samsung channel lists are now loaded/saved correctly 
  (program numbers, favorites, locking, frequencies, ...)
- loading a reference list for a Samsung .SCM file which contains both
  air and cable channels or satellite and AstraHD+ channels caused the 
  items to be mixed up and all shown in the first list (showing not-found
  channels in red)

2013-03-30
- FIX: bei nicht-LM Ger�ten wurden die DVB-S Programmnummern falsch ausgelesen
- Hotelmodus/DTV-channel-update kann nun bei allen LG serien ge�ndert werden

2013-03-29
- LG: Doppelt vorhandene Sender (die automatisch vom TV bei der Sendersuche
  mit L�ndervoreinstellung angelegt werden) werden nun automatisch gel�scht.
  Diese f�hren am TV h�ufig dazu, dass Sender zuf�llig zwischen deren
  Programmpl�tzen hin- und herspringen. (Bug im TV, unabh�ngig von ChanSort)
- LG: Sender k�nnen nun gel�scht werden ("Nicht explizit sortierte Sender: L�schen")
- LG: �ndern von Sendernamen m�glich (um bei DVB-C/T/S die Namen nicht wieder
  zu verlieren, muss Hotel-Mode=ein und DTV channel update="manual" sein)
- LG: F�r die LM-Serie kann nun innerhalb von ChanSort der Hotel-Modus bzw
  die Senderlisten-Aktualisierung ein-/ausgeschaltet werden.

2013-02-26
- Neuer Bearbeitungsmodus "Tauschen" eingebaut, mit dem beim �ndern der
  Programmnummer die beiden Sender ihre Nummer tauschen und alle anderen
  Nummern unver�ndert bleiben.
- Beim �ffnen einer TV-Datei ohne zugeh�riger Referenzliste werden nun
  automatisch alle Sender in die "Sortierte Liste" �bernommen.
- "Speichern unter" funktioniert nun auch mit Samsung's SCM Dateien
- Wenn beim Speichern ein Fehler auftritt, wird nun auf m�gliche Ursachen 
  hingewiesen

2013-02-11
- Mehrfach vorhandene Sender werden nun getrennt angezeigt, wenn sie 
  unterschiedlichen Programmnummern zugewiesen sind (z.B. DVB-T Empfang des 
  gleichen Senders �ber verschiedene Sendeanlagen).
- Beim �ndern der Programmnr auf eine bisher nicht verwendete Nummer werden
  die Programmnummern hinter der neuen Nummer nicht mehr erh�ht.

2013-02-04
- Unterst�tzung f�r Samsung "AstraHDPlus" Senderliste hinzugef�gt
- Funktion zum �bernehmen der bestehenden Senderliste in die sortierte Liste

2013-01-22
- Fix: Import von .chl Referenzlisten, wenn der gleiche Sendername �ber
  mehrere Satelliten empfangen wird und dort dem gleichen TSID zugewiesen ist.

2013-01-16
- Import von .chl Referenzlisten von SamToolBox
- Samsung Senderlisten zeigen nun "verschl�sselt"-Info an
- FIX: Mehrfachauswahl in den Senderlisten (mit Strg/Shift + Maus/Cursortasten)
- FIX: Warnung statt Absturz bei mehrfach vergebenen Transponder-IDs (.SCM Datei)

2013-01-15
- Samsung Serie E wird nun unterst�tzt
- Favoritenliste der Samsung Serie D und E  wird nun erkannt
- Samsung Modellerkennung verbessert

2012-12-26
- Unterst�tzung f�r Samsung Fernseher hinzugef�gt
- Funktion zum �ffnen einer Referenzliste hinzugef�gt
- Funktion zum kompletten L�schen der Senderlisten f�r LG Fernseher
- Diverse Bugfixes

2012-11-07
- Anzeige von DVB Netzwerk Name und Betreiber
- Anzeige der DVB-S Transpondernummer
- Fix: Direkte Eingabe der Prog# in rechter Liste, wenn sie vorher 0 war

2012-11-06
- Fix: Analoge Senderliste wurde nicht korrekt gespeichert
- Fix: Hinzuf�gen von Sendern zu einer leeren Liste
- Setzen von Favoriten m�glich
- Setzen von Sender sperren / �berspringen / verstecken
- Direkte Eingabe von neuer Programmnr in den Tabellen
- Kontextmen� �ber rechte Maustaste

2012-11-05
- Fix: DVB-C/T Senderliste wurde nicht korrekt gespeichert
- Fix: Favoriten in DVB-C/T werden nun korrekt angezeigt

2012-11-04
- Fix: Transpondernummer und Satelliteninfo wurde falsch ausgelesen
- Mehrfach vorhandene Sender werden nun nicht mehr ausgefiltert

2012-11-01
- UI und internes Datenmodell komplett �berarbeitet
- Getrennte Listen f�r Analog, DVB-C/T, DVB-S in jeweils Radio/TV

2012-10-30
- Unterst�tzung f�r LG Serie CS, LD, LE, LH und PM hinzugef�gt
- Neue Serien k�nnen durch Anpassen einer .INI Datei hinzugef�gt werden
- Automatischer Test im Sourcecode, der alle bekannten TLLs l�dt
- Hilfe-Men� hinzugef�gt

2012-10-29
- Plugin zum direkten Laden/Speichern von TLLs, ohne TLLsort.exe
- Unterst�tzung f�r LG Serie LV und LW hinzugef�gt
- Sourcen ver�ffentlicht

2012-10-26
- Programm umbenannt von TLLsortGUI auf ChanSort
- �bersetzt in Englisch und �sterreichisch
- Einstellungen werden beim Beenden/Speichern des Programms �bernommen
- Ausgew�hlten Zeilen in der sortierten Liste alphabetisch sortieren
- Dateinamen f�r Speichern k�nnen ge�ndert werden
- Unterst�tzung f�r Plugin-DLLs f�r verschiedene TV-Modelle

2012-10-25
- Neu: Wenn eine Gruppenzeile (Sat, Analog, CableAndTerrestic) ausgew�hlt
  ist, werden alle darin enthaltene Sender eingef�gt bzw. entfernt.
- Bugfix: Eingabefelder f�r Einf�gepositionen erlauben nun keine 
  ung�ltigen (sprich zu hohe, nicht fortlaufende) Nummern mehr.

2012-10-24 (14:52 MESZ)
- Bugfix: Fehler beim Einlesen der TLL-Datei, wenn der gleiche Sender 
  (sprich Uid) mehrfach enthalten war. Kann vermutlich passieren, wenn 
  ein Sendersuchlauf 2x durchgef�hrt wurde, ohne die alten Programme zu
  l�schen.

2012-10-24 (#1)
- erste Ver�ffentlichung