# Computer-Architecture-lab2-Design-Space-Exploration-with-gem5

# 2η Εργαστηριακή Άσκηση Αρχιτεκτονικής Υπολογιστών

## Design Space Exploration με τον gem5

**Γιακουμάκης Αθανάσιος ΑΕΜ 8554**

**Θεοδοσιάδης Κωνσταντίνος ΑΕΜ 8296**

### Ερωτήματα Δεύτερου Μέρους

#### Βήμα 1ο

Για το Βήμα 1ο εκτελέσαμε πέντε benchmarks τα οποία ανήκουν στα SPECcpu2006 benchmarks και παρακάτω σας παρουσιάζουμε τα αποτελέσματα που μας ζητήθηκαν από την εκφώνηση της εργαστηριακής άσκησης.

#### Ερώτημα 1

Αφού εκτελέσαμε τα πέντε benchmarks στον gem5 και μελετήσαμε τα αρχεία config.ini και config.json παρουσιάζουμε παράκατω βασικές παραμέτρους για τον επεξεργαστή που εξομοιώνει ο gem5 όσον αφορά το υποσύστημα μνήμης.

**1.Μέγεθος L1 instruction cache**

Το μέγεθος της L1 instruction cache είναι 32kB.

**config.ini**

>[system.cpu.icache]

>size=32768

**config.json**

>"system": "system",

>"path": "system.cpu.icache.tags",

>"size": 32768

**2.Μεγεθός L1 data cache**

Το μέγεθος της L1 data cache είναι 64kB.

**config.ini**

>[system.cpu.dcache]

>size=65536

**config.json**

>"system": "system",

>"path": "system.cpu.dcache.tags",

>"size": 65536

**3.Μέγεθος L2 cache**

Το μέγεθος της L2 cache είναι 2097kB.

**config.ini**

>[system.l2]

>size=2097152

**config.json**

>"system": "system",

>"path": "system.l2.tags",

>"size": 2097152

**4.Αssociativity L1 instruction cache**

Το associativity της L1 instruction cache είναι 2(two-way set associative).

**config.json**

>[system.cpu.icache]

>assoc=2

**config.json**

>"system": "system",

>"path": "system.cpu.icache.tags",

>"assoc": 2,

**5.Αssociativity L1 data cache**

Το associativity της L1 data cache είναι 2(two-way set associative).

**config.ini**

>[system.cpu.dcache]

>assoc=2

**config.json**

>"system": "system",

>"path": "system.cpu.dcache.tags",

>"assoc": 2,

**6.Αssociativity L2 cache**

Το associativity της L2 cache είναι 8(eight-way set associative).

**config.ini**

>[system.l2]

>assoc=8

**config.json**

>"system": "system", 

>"path": "system.l2.tags",

>"assoc": 8,

**7.Μέγεθος cache line**

Το μέγεθος της cache line είναι 64 bytes.

**config.ini**

>[system]

>cache_line_size=64

**config.json**

>"cache_line_size": 64,


#### Ερώτημα 2

Σε αυτό το ερώτημα μας ζητήθηκε να καταγράψουμε συγκεκριμένα αποτελέσματα για κάθε benchmark που εξομοιώσαμε στον gem5.

**1. 401.bzip2 benchmark**

_1.Χρόνος εκτέλεσης_

>sim_seconds 0.161337

_2.Cycles per instruction_

>system.cpu.cpi 1.613367

_3.L1 instruction cache miss rate_

>system.cpu.icache.overall_miss_rate::total 0.000074

_4.L1 data cache miss rate_

>system.cpu.dcache.overall_miss_rate::total 0.014683

_5.L2 cache miss rate_

>system.l2.overall_miss_rate::total 0.281702

**2. 429.mcf benchmark**

_1.Χρόνος εκτέλεσης_

>sim_seconds 0.109125

_2.Cycles per instruction_

>system.cpu.cpi 1.091249

_3.L1 instruction cache miss rate_

>system.cpu.icache.overall_miss_rate::total 0.002051

_4.L1 data cache miss rate_

>system.cpu.dcache.overall_miss_rate::total 0.000037

_5.L2 cache miss rate_

>system.l2.overall_miss_rate::total 0.724040

**3. 456.hmmer benchmark**

_1.Χρόνος εκτέλεσης_

>sim_seconds 0.118453

_2.Cycles per instruction_

>system.cpu.cpi 1.184534

_3.L1 instruction cache miss rate_

>system.cpu.icache.overall_miss_rate::total 0.001638

_4.L1 data cache miss rate_

>system.cpu.dcache.overall_miss_rate::total 0.000205

_5.L2 cache miss rate_

>system.l2.overall_miss_rate::total 0.082233

**4. 458.sjeng benchmark**

_1.Χρόνος εκτέλεσης_

>sim_seconds 0.704063

_2.Cycles per instruction_

>system.cpu.cpi 7.040633

_3.L1 instruction cache miss rate_

>system.cpu.icache.overall_miss_rate::total 0.121829

_4.L1 data cache miss rate_

>system.cpu.dcache.overall_miss_rate::total 0.000020

_5.L2 cache miss rate_

>system.l2.overall_miss_rate::total 0.999979

**5. 470.lbm benchmark**

_1.Χρόνος εκτέλεσης_

>sim_seconds 0.262355

_2.Cycles per instruction_

>system.cpu.cpi 2.623555

_3.L1 instruction cache miss rate_

>system.cpu.icache.overall_miss_rate::total 0.060971

_4.L1 data cache miss rate_

>system.cpu.dcache.overall_miss_rate::total 0.000099

_5.L2 cache miss rate_

>system.l2.overall_miss_rate::total 0.999927

Εφόσον,εντοπίσαμε αυτές τις πληροφορίες δημιουργήσαμε κάποια γραφήματα όπου σε κάθε ένα παρουσιάζουμε την αντίστοιχη τιμή για κάθε benchmark.

**1.Χρόνος εκτέλεσης(sim_seconds)**
 

![sim](https://user-images.githubusercontent.com/57605047/70481082-2c87fb00-1aea-11ea-9156-fa3a53efcb2b.png) 


Παρατηρώντας τις καταγραφές μας αλλά και το σχετικό γράφημα βλέπουμε ότι για τα bencmarks 401.bzip2,429.mcf,456.hmmer έχουν κοντινό χρόνο εκτέλεσης και κάτω από 0,2 seconds,το benchmark 470.lbm έχει χρόνο εκτέλεσης πάνω από 0,2 seconds ενώ το 458.sjeng benchmark έχει πολύ μεγαλύτερο χρόνο εκτέλεσης από τα υπόλοιπα,λίγο παραπάνω από 0,7 seconds.

**2.Cycles per instruction**

![CPI](https://user-images.githubusercontent.com/57605047/70481260-b932b900-1aea-11ea-9d80-758fff44d66d.png)



Στο κομμάτι που αφορά βλέπουμε ότι είναι ανάλογο του χρόνου εκτέλεσης(sim_seconds*10).Τα benchmarks 429.mcf και 456.hmmer έχουν αρκετά καλό CPI,κοντά στο 1.Το 401.bzip2 έχει 1,6 και το 470.lbm έχει 2,6 κάτι που δεν έιναι καθόλου καλό.Όσο για το 458.sjeng το CPI είναι στα 7 κάτι που είναι πάρα πολύ υψηλό.

**3.L1 instruction cache miss rate**

![L1i](https://user-images.githubusercontent.com/57605047/70481343-f26b2900-1aea-11ea-9c1e-606f8a881da4.png)



Εδώ τα πιο χαμηλά miss rates τα έχουν τα 429.mcf και 458.sjeng.Τα benchmarks 401.bzip2 και 470.lbm έχουν miss rates τα επιδέχονται βελτίωσης και πολύ υψηλό έχει 456.hmmer.

**4.L1 data cache miss rate**

![L1d](https://user-images.githubusercontent.com/57605047/70481359-ff881800-1aea-11ea-8ba1-ec08ad4eaa4a.png)



Πολύ χαμήλο miss rate έχουν τα 429.mcf,456.hmmer και επίσης χαμηλό έχει το 401.bzip2.Υψηλό έχει το 470.lbm ένω διπλάσιο από αυτό έχει 458.sjeng.

**5.L2 cache miss rate**

![L2](https://user-images.githubusercontent.com/57605047/70481369-0ca50700-1aeb-11ea-937d-3560f570771e.png)



Για το L2 cache miss rate χαμηλό έχει το 456.hmmer.Το 401.bzip2 έχει λίγο πιο μεγάλο από 0,2,το 429.mcf έχει σχεδόν 0,7.Τα benchmarks 458.sjeng και 470.lbm έχουν πολύ υψηλό,σχεδόν 1.

#### Ερώτημα 3

Σε αυτό το ερώτημα εφόσον έχουμε τρέξει τα benchmarks ρυθμίζοντας μία το ρολόι του επεξεργαστή στα 1GHz και μία στα 2GHz μελετήσαμε τα αρχεία stats.txt και εντοπίσαμε τις παρακάτω πληροφορίες.

**stats.txt_CPUclock_1GHz**

>system.clk_domain.clock 1000 # Clock period in ticks

>system.cpu_clk_domain.clock 1000 # Clock period in ticks

**stats.txt_CPUclock_2GHz**

>system.clk_domain.clock 1000 # Clock period in ticks

>system.cpu_clk_domain.clock 500 # Clock period in ticks

Αυτό που βλέπουμε είναι ότι ότι αυτό που χρονίζεται στα 1GHz είναι το ρολόι του συνολικού συστήματος,τα στοιχεία της μητρικής κάρτας,έτσι ώστε το όλα αυτά να δουλεύουν συγχρονισμένα.Το συγκεκριμένο ρολόι ορίζεται να είναι παραπάνω από τον περισσότερο χρόνο που παίρνει για οποιοδήποτε σήμα να διαδοθεί μέσω οποιουδήποτε κυκλώματος της κάρτας οπότε δεν υπάρχει κίνδυνος κάποιο σήμα να φτάσει πριν να είναι έτοιμα άλλα σήματα.Το ρολόι του επεξεργαστή(CPU) εξυπηρετεί την ίδια λειτουργία αλλά για τα στοιχεία που το αποτελούν και επειδή συνήθως ένας επεξεργαστής πρέπει να εκτελεί περισσοτέρες λειτουργίες ανα μονάδα χρόνου συνήθως έχει μεγαλύτερη τιμή από αυτή του ρολογιού του συνολικού συστήματος.Επειδη,όμως θέλουμε αυτά τα δύο τα συγχρονίζονται,η τίμη του ρολογιού του επεξεργαστή είναι πολλαπλάσιο της τιμής του ρολογιού του συστήματος,για αυτό και μελετώντας τα αρχεία stats.txt βλέπουμε ότι το ένα εκφράζεται ως πολλαπλάσιο του άλλου.Επίσης,μελετώντας το αρχείο config.json βλέπουμε ότι όλα τα στοιχεία της CPU,όπως περιμέναμε,χρόνιζονται με το ρολόι του επεξεργαστή.Επειδή,έχουμε ορίζει Minor model αυτά είναι:

1.L1 data cache

2.L1 instruction cache

3.L2 cache 

4.instruction walker cache

5.data walker cache

6.οι δίοδοι που συνδέουν τα παραπάνω μεταξύ τους αλλά και με την SDRAM. 

Αν προσθέσουμε άλλον ένα επεξεργαστή στο σύστημα τότε αυτός θεωρούμε ότι τα πρέπει να χρονιστεί με το ρολόι του συστήματος.Αν προσθέσουμε άλλο ένα πυρήνα τότε το πως θα χρονιστεί αυτός έχει να κάνει με την αρχιτεκτονική του επεξεργαστή,φυσικά το ρολόι του θα είναι πολλαπλάσιο του ρολογιού του συστήματος.
Αυτό που παρατηρήσαμε είναι στα benchmarks 429.mcf,401.bzip2,470.lbm και 456.hmmer υπάρχει αρκετά καλό scaling ενώ στο 458.sjeng δεν είναι καθόλου καλό.Φυσικά,το τέλειο scaling στην συγκεκριμένη περίπτωση είναι πολύ δύσκολο να επιτευχθεί διότι η απόδοση του συστήματος όσο αναφορά τον χρόνο εκτέλεσης δεν καθορίζεται μόνο απο το ρολόι του επεξεργαστή αλλά και πολλές άλλες παραμέτρους του συστήματος(π.χ χαρακτηριστικά τωνς caches).

#### Βήμα 2ο

Σε αυτό το βήμα μας ζητήθηκε να βρούμε τον κατάλληλο συνδιασμό επτά παραμέτρων για τον οποίο το CPI(cycles per instruction) βελτιώνεται για κάθε benchmark και να παρουσιάσουμε με την μορφή γραφημάτων πως η αλλαγή κάθε παραμέτρου από αυτές επηρέαζει την απόδοση κάθε benchmark.

#### Ερώτημα 1

Ο συνδιασμός που παρατηρήσαμε ότι βελτιώνει σε μεγάλο βαθμό το CPI(cycles per instruction) όλων των benchmarks παρουσιάζεται παρακάτω:

**1.L1 data cache size**

Ορίστηκε μέσω της γραμμής εντολών κατά την κλήση του gem5 ως option του configuration script se.py(--l1d_size=) στα 128kΒ.

**2.L1 data cache associativity**

Ορίστηκε μέσω της γραμμής εντολών κατά την κλήση του gem5 ως option του configuration script se.py(--l1d_assoc=) στο 8.

**3.L1 instruction cache size**

Ορίστηκε μέσω της γραμμής εντολών κατά την κλήση του gem5 ως option του configuration script se.py(--l1i_size=) στα 64kΒ.

**4.L1 instruction cache associativity**

Ορίστηκε μέσω της γραμμής εντολών κατά την κλήση του gem5 ως option του configuration script se.py(--l1i_assoc=) στο 8.

**5.L2 cache size**

Ορίστηκε μέσω της γραμμής εντολών κατά την κλήση του gem5 ως option του configuration script se.py(--l2_size=) στα 4096kΒ(4ΜΒ).

**6.L2 cache associativity**

Ορίστηκε μέσω της γραμμής εντολών κατά την κλήση του gem5 ως option του configuration script se.py(--l2_assoc=) στο 8.

**7.Cache line size**

Ορίστηκε μέσω της γραμμής εντολών κατά την κλήση του gem5 ως option του configuration script se.py(--cacheline_size=) στα 512 bytes.

Εφόσον,εκτελέσαμε τα benchmarks κάνοντας χρήση των παραπάνω μελετήσαμε έπειτα στο αρχείο stats.txt το πεδίο του CPI(cycles per instruction) για κάθε benchmark και τα συγκρίναμε με τις τιμές που πήραμε στο 1ο Ερώτημα του 1ου Βήματος.

**1. 401.bzip2 benchmark**

To CPI(cycles per instruction) του benchmark ήταν 1.613367
και κάνοντας κλήση του gem5 με τον συνδιασμό των ορισμάτων που παρουσιάσαμε παραπάνω έγινε 1.564110.To 401.bzip2 benchmark αυτό που εκτελεί είναι η συμπίεση και η αποσυμπίεση έξι αρχείων και είδαμε οτί η αύξηση του μέγεθους των caches είχε θετικό αντίκτυπο πάνω στην απόδοση του.

**2. 429.mcf benchmark**

Το CPI(cycles per instruction) του ήταν στα 1.091249 και το μειώσαμε στα 1.062495.Προφανώς η απόδοση του συγκεκριμένου benchmark ήταν ήδη πάρα πολύ ικανοποιητική και η βελτίωση που επιφέραμε είναι πολύ μικρή.Αυτό που κάνει το συγκεκριμένο benchmark είναι να υπολογίζει την βέλτιστη λύση σε ένα πρόβλημα όπου έχουμε κάποια δρομολόγια με συγκεκριμένα κόστη και ένα στόλο από οχήματα και πρέπει να κάνουμε την ανάθεση των δρομολογίων με τον καλύτερο τρόπο.Ο αναμενόμενος χρόνος εκτέλεσης είναι της τάξης ενός χαμηλόβαθμου πολυωνύμου λόγω του γρήγορου και απλού τρόπου που γίνεται η παραπάνω διαδικασία.

**3. 456.hmmer benchmark**

Το CPI(cycles per instruction) του ήταν 1.184534 και το μειώσαμε στο 1.177381.Η διεργασία που εκτελεί το benchmark είναι η αναζήτηση σε μία βάσης δεδομένων γονιδίων.

**4. 458.sjeng benchmark**

Το CPI(cycles per instruction) του ήταν 7.040633,το πιο υψηλό από όλα τα υπόλοιπα,και το ρίξαμε στο 3.070681.Το 458.sjeng benchmark έχει βασιστεί σε ένα πρόγραμμα το οποίο παίζει σκάκι,και άλλες παραλλαγές του,και προσπαθεί να υπολογίσει την καλύτερη σειρά κινήσεων για 9 θέσεις σε διάφορες φάσεις του παιχνιδιού κάνοντας αναζήτηση σε ένα δένδρο με ενναλακτικές αναλόγως με το βάθος που έχει οριστεί.Αυτό που παρατηρήσαμε για το συγκεκριμένο benchmark έιναι ότι είχε πολύ μεγάλο ποσοστό αστοχιών στην L2 cache κάτι που επηρεάζει πολύ την απόδοση του και ότι όσο μεγαλώναμε το μέγεθος της γραμμής της cache τόσο βελτιωνόταν σε μεγάλο βαθμό.Αυτό ίσως οφείλεται στο ότι επειδή κάνει αναζήτηση σε ένα δένδρο υπάρχει ισχυρό spatial locality.

**5. 470.lbm benchmark**

Το CPI(cycles per instruction) του 470.lbm benchmark δεν ήταν επίσης καλό,2.623555,αλλά μειώθηκε στα 1.491551 που είναι μία πάρα πολύ καλή βελτίωση.Και αυτό το benchmark είχε υψηλό ποσοστό αστοχιών στην L2 cache.To benchmark αυτό που κάνει κατα την εκτέλεση του έιναι η εφαρμογή μίας συγκεκριμένης μεθόδου(Lattice Boltzmann Method) για να προσομοιώσει ασυμπίεστα υγρά σε 3D μορφή.Και σε αυτήν την περίπτωση υπάρχει ισχυρό spatial locality άρα η αύξηση του μεγέθους της γραμμής των caches βελτίωσε σε μεγάλο βαθμό την απόδοση.

#### Ερώτημα 2

Σε αυτό το ερώτημα θα παρουσιάσουμε την επίδραση κάθε ενός παράγοντα στην απόδοση των benchmarks(CPI) με την μορφή γραφημάτων.Να τονίσουμε ότι κάθε φορά που αλλάζαμε την τιμή μίας παραμέτρου οι υπόλοιπες είχαν την τιμή που δίνεται by deafault και τις οποίες έχουμε καταγράψει στο Ερώτημα 1ο του 1ου Βήματος.


**1.L1 data cache size**

![L1dcs](https://user-images.githubusercontent.com/57605047/70481403-26464e80-1aeb-11ea-9cf1-1bd97f6576c7.png) 


Αυτό που βλέπουμε σε αυτό το γράφημα είναι ότι η αλλαγή του μεγεθούς της L1 data cache επηρεάζει θετικά την απόδοση του 401.bzip2 benchmark ενώ σε όλα τα άλλα έχει αμελητέα επίδραση.Πιστεύουμε ότι αυτό είναι λογικό λόγω της λειτουργίας του συγκεκριμένου benchmark που περιγράψαμε παραπάνω,εφόσον τα αρχεία που επεξεργάζεται δεν είναι πολύ μεγάλου μεγέθους.


**2.L1 data cache associativity**

![L1dca](https://user-images.githubusercontent.com/57605047/70481424-3827f180-1aeb-11ea-80fa-93acde83bffc.png)


Το associativity της L1 data cache δεν φαίνεται να επηρεάζει την επίδοση κανενός benchmark το οποίο πιστεύουμε ότι οφείλεται στα μικρά miss rates που καταγράψαμε κατα την εκτέλεση τους με default ορίσματα στο Βήμα 1ο.

**3.L1 instruction cache size**

![L1ics](https://user-images.githubusercontent.com/57605047/70481467-57bf1a00-1aeb-11ea-8733-c4167443a9d0.png) 

Αρχικά,σε αυτό το γράφημα πάλι παρατηρούμε ότι στα περισσότερα benchmarks οι μεταβολές στο μέγεθος της L1 instruction cache δεν επηρεάζουν την απόδοση των benchmarks σε πολύ μεγάλο βαθμό.Αυτό που έχει ενδιαφέρον είναι ότι στο 429.mcf benchmark βλέπουμε μία βελτίωση στην απόδοση όταν το μέγεθος της cache γίνεται μεγαλύτερο απο 16kB.Μην ξεχνάμε ότι στα περισσότερα προγράμματα τα accesses που γίνονται στην instruction cache είναι περισσότερα από αυτά που γίνονται στην data cache οπότε είναι αναμενόμενος ο αντίκτυπος στην επίδοση αν δούμε και την λειτουργία του 429.mcf που έχουμε παρουσιάσει παραπάνω.

**4.L1 instruction cache associativity**

![L1ica](https://user-images.githubusercontent.com/57605047/70481485-61488200-1aeb-11ea-934c-b2257c522d82.png)


Αντίστοιχα και με το associacitivity της L1 data cache και εδώ δεν περιμέναμε να δούμε μεγάλες μεταβολές στην απόδοση επειδή είχαμε παρατηρήσει ότι τα miss rates αυτής της cache ήταν πολύ μικρά στις εκτελέσεις όλων των benchmarks.

**5.L2 cache size**

![L2csr](https://user-images.githubusercontent.com/57605047/70481500-6c9bad80-1aeb-11ea-8678-31e3d3449925.png) 

Σε αυτό το γράφημα παρατηρούμε ότι η αύξηση του μεγέθους της L2 cache έχει θετικό αντίκτυπο στην απόδοση όλων των benchmarks κάτι που είναι αναμενομένο αφού το miss penalty στην L2 cache έχει μεγάλυτερο αντίκτυπο στην απόδοση από αυτό που έχουν οι L1 caches.

**6.L2 cache associativity**

![L2ca](https://user-images.githubusercontent.com/57605047/70481512-78876f80-1aeb-11ea-807b-47aff017d17e.png)
 

Παρατηρούμε ότι αύξηση του associativity της L2 cache δεν έχει σημαντική επίδραση στην απόδοση κάποιου benchmark.Ίσως αυτό οφείλεται στο μέγεθος της cache που είναι by deafult ορισμένο στα 2 ΜΒ.

**7.Cache line size**

![Cls](https://user-images.githubusercontent.com/57605047/70481520-82a96e00-1aeb-11ea-928c-345d0c5b1fbb.png) 

Η συγκεκριμένη παράμετρος είχε την μεγαλύτερη επίδραση πάνω στο CPI(cycles peρ instruction) στην εκτέλεση των παραπάνω benchmarks.Εδώ βλέπουμε ότι στα 458.sjeng και 470.lbm έχουμε τεράστια βελτιώση όσο μεγαλώνουμε το μέγεθος της γραμμής των caches κάτι που πιστεύουμε ότι οφείλεται στο γεγονός ότι εκμεταλλευόμαστε σε μεγαλύτερο βαθμό το ισχυρό spatial locality τους.Αντίθετα,στα benchmarks 401.bzip2 και 429.mcf ενώ βλέπουμε μία αρχική βελτίωση στην απόδοση,όταν αυξήσουμε το μέγεθος της γραμμής των caches στα 1024kB το CPI(cycles per instruction) μεγαλώνει κάτι που είναι αποτέλεσμα της αύξησης του miss penalty και των conflict misses τα οποία αυξάνονται όσο μεγαλώνει το μέγεθος της γραμμής.

#### Βήμα 3ο

Σε αυτό το βήμα μας ζητήθηκε να θέσουμε μία συνάρτηση κόστους και απόδοσης έτσι ώστε μελετώντας τα αποτέλεσματα που πήραμε από το Βήμα 2ο να καταλήξουμε στην καλύτερη  αρχιτεκτονική που βελτιστοποιεί την απόδοση του συστήματος σε σχέση με το κόστος του.Αυτή η συνάρτηση είναι η:

>F(Perf,Cost)=Perf() + Cost()

Για την συνάρτηση Cost() έπειτα από μελέτη κάναμε τις εξής παραδοχές:

**1.** Ότι το κόστος της υλοποίησης μίας n-way set associative cache είναι κοινό είτε είναι L1 cache είτε είναι L2 cache αφού υποθέτουμε ότι η πολυπλοκότητα αυξάνεται το ίδιο.

**2.** Ότι η υλοποίηση μίας L1 cache ως προς το μέγεθος έχει αναλογία 1:8 με την ίδια υλοποίηση μίας L2 cache.Δηλαδή μία L1 cache του 1kB θα κοστίζει όσο μία L2 cache των 8kB.

**3.** Για το cache line size κάναμε την παραδοχή ότι όποτε διπλασιάζεται τότε διπλασιάζεται και το κόστος του.
 
 Στον παρακάτω πίνακα ορίσαμε για ποιές τιμές της κάθε παραμέτρου το κόστος είναι ίσο με ένα(1) και ορίσαμε και το κόστος για κάποιες άλλες τιμές έτσι ώστε να γίνουν πιο κατανοητές οι παραδοχές που κάναμε σχετικά με το πόσο θα κοστίζει κάθε παράμετρος.
 
| **C()** | **L1dsize** | **L1dassoc** | **L1isize** | **L1iassoc** | **L2size** | **L2assoc** | **cache line size** |
| ------- | ----------- | ------------ | ----------- | ------------ | ---------- | ----------- | ------------------- |
| 1 | 32kB | 2 | 32kB | 2 | 256kB | 2 | 64bytes |
| 2 | 64kB | 4 | 64kB | 4 | 512kB | 4 | 128bytes |
| 4 | 128kB | 8 | 128kB | 8 | 1024kB | 8 | 256bytes |

Οπότε η συνάρτηση Cost() θα υπολογίζεται ως εξής:

>Cost(L1dsize,L1dassoc,L1isize,L1iassoc,L2size,L2assoc,cls)=C(L1ds)+C(L1da)+C(L1is)+C(L1id)+C(L2s)+C(L2a)+C(cls)

*όπου cls σημαίνει **c**ache **l**ine **s**ize

Δηλαδή το άθροισμα του κόστους για την υλοποίηση κάθε στοιχείου.

Για την συνάρτηση Perf(CPI) θεωρήσαμε ότι η τιμή της θα υπολογίζεται ως εξής:

>Perf(CPI)=2*CPI

Όπου το CPI είναι αυτό που παίρνουμε για την εκτέλεση ενός benchmark με κάποιο συνδιασμό των γνωστών παραμέτρων.Με αυτό τον τρόπο στην συνάρτηση F(Perf,Cost) όταν το CPI αυξηθεί κατα 0.5 θα επηρέασει το αποτέλεσμα που παράγει η συνάρτηση όσο και αν το κόστος αυξηθεί κατα 1 μονάδα.

Οπότε για τον υπολογισμού ενός μέτρου απόδοσης και κόστους θα πέρνουμε απο την συνάρτηση Cost() μια τιμή για μία υλοποίηση που κάναμε και θα την προσθέτουμε με την συνάρτηση Perf() που πήραμε τρέχοντας κάποιο benchmark με αυτή.Για την υλοποίηση που αυτό το άθροισμα είναι το μικρότερο θα λέμε ότι είναι η βέλτιστη για το συγκεκριμένο benchmark.

Συνολικά μελετώντας τις μετρήσεις που είχαμε από το Βήμα 2ο από τις εξομοιώσεις που κάναμε καταλήξαμε στις εξής βέλτιστες αρχιτεκτονικές για κάθε benchmark:

**1. 401.bzip2 benchmark**

L1 data cache size:16kB

L1 data cache associativity:2

L1 instruction cache size:16kB

L1 instruction cache associativity:2

L2 cache size:256kB

L2 cache associativity:2

Cache line size:32bytes

**2. 429.mcf benchmark**

L1 data cache size:16kB

L1 data cache associativity:2

L1 instruction cache size:32kB

L1 instruction cache associativity:2

L2 cache size:256kB

L2 cache associativity:2

Cache line size:32bytes

**3. 456.hmmer benchmark**

L1 data cache size:16kB

L1 data cache associativity:2

L1 instruction cache size:16kB

L1 instruction cache associativity:2

L2 cache size:256kB

L2 cache associativity:2

Cache line size:32bytes

**4. 458.sjeng benchmark**

L1 data cache size:16kB

L1 data cache associativity:2

L1 instruction cache size:16kB

L1 instruction cache associativity:2

L2 cache size:256kB

L2 cache associativity:2

Cache line size:256bytes

**5. 470.lbm benchmark**

L1 data cache size:16kB

L1 data cache associativity:2

L1 instruction cache size:16kB

L1 instruction cache associativity:2

L2 cache size:256kB

L2 cache associativity:2

Cache line size:128bytes

**Συνολικά η καλύτερη αρχιτεκτονική που έχουμε να προτείνουμε είναι η εξής:**

L1 data cache size:16kB

L1 data cache associativity:2

L1 instruction cache size:16kB

L1 instruction cache associativity:2

L2 cache size:256kB

L2 cache associativity:2

Cache line size:128bytes

Και αυτό διότι παρατηρήσαμε ότι κατα την εκτέλεση όλων των benchmarks παίρνουμε ως αποτέλεσμα πολύ καλό CPI και σύμφωνα με την συνάρτηση Cost() έχει αποδεκτό κόστος.Στην ουσία θεωρούμε ότι το by default ορισμένο μέγεθος της Level 2 cache στα 2ΜΒ είναι ανώφελο από άποψη απόδοσης-κόστους οπότε και το μειώσαμε στα 256kB όπως και το associativity που είναι ορισμένο στα by default στα 8 και το κάναμε 2.Τέλος,το μέγεθος της γραμμής των caches το μεγαλώσαμε από 64bytes στα 128bytes,δηλαδή το διπλασιάσαμε,επειδή παρατηρήσαμε ότι επηρεάζει θετικά σε μεγάλο βαθμό την απόδοση όλων των benchmarks και δεν έχει τεράστια διαφορά κόστους από τα 64bytes.


#### Σημαντική σημείωση

Η έκδοση του gem5 που χρησιμοποιούμε για την εκπόνηση της εργασίας είχε by default το ρολόι της CPU στα 2GHz.Έμεις κατα την επίλυση όλων των βημάτων και την συλλογή όλων των αποτελεσμάτων ορίζαμε μέσω της γραμμής εντολών(--cpu-clock=1GHz) το ρολόι της CPU να είναι **1GHz**.Επίσης,τα αποτελέσματα που μας έδωσε ο gem5 από όλες τις εξομοιώσεις που κάναμε θα τα βρείτε στον φάκελο Computer-Architecture-lab2-Design-Space-Exploration-with-gem5.

#### Λίγα λόγια από εμάς

Την συγκεκριμένη εργασία την απολαύσαμε παρα πολύ για τον λόγο του ότι ήτανε μία πολύ καλή εισαγωγή στον τρόπο σκέψης των αρχιτεκτόνων υπολογιστών.Επίσης,μας άρεσε το ότι μας έδωσε περιθώριο στο να κάνουμε δικές μας επιλογές και μας έβαλε σε μία διαδικασία να τις υποστηρίξουμε βελτιώνοντας κατα πολύ την οπτική μας και τον τρόπο σκέψη μας πάνω στην αρχιτεκτονική ενός επεξεργαστή.Φυσικά,είναι πολύ πιθανό να έχουμε φτάσει σε λάθος συμπεράσματα και θα θέλαμε πολύ να μας να επισημάνετε και να μας τα επισημάνετε.Ένα λάθος που εντοπίσαμε στην εκφώνηση ήταν στην εντολή που δίνεται:

>./build/ARM/gem5.opt -d spec_results/specsjeng configs/example/se.py --cpu-type=MinorCPU --caches --l2cache -c spec_cpu2006/458.sjeng/src/specsjeng-o "spec_cpu2006/458.sjeng/data/test.txt" -I 100000000

χρειάζεται ένα κενό πριν το -ο αλλίως βγάζει error σχετικό με τα positional arguments.Τέλος,προσωπικά εμείς αντιμετωπίσαμε κάποιες ασάφειες κατα κύριο λόγο σχετικές με τα ζητούμενα του Βήματος 2 και Βήματος 3 σχετικές με το πότε πρέπει να προτείνουμε μία αρχιτεκτονική για κάθε benchmark ξεχωριστά και πότε μια συνολική για όλα.Ευτυχώς,ο κ.Μπροκαλάκης Ανδρέας ήταν πάρα πολύ βοηθητικός απέναντι μας και μας επίλυσε άμεσα οποιαδήποτε απορία είχαμε.


#### Βιβλιογραφία

1.gem5 simulator wiki [http://gem5.org/Main_Page](http://gem5.org/Main_Page) 

2.Difference Between System Clock and CPU Clock [https://anydifferencebetween.com/difference-between-system-clock-and-cpu-clock/](https://anydifferencebetween.com/difference-between-system-clock-and-cpu-clock/) 

3.Cache Lines and Cache Size Chapter 3. Introduction to Caches [https://docs.roguewave.com/threadspotter/2010.4/manual/ch03s02.html](https://docs.roguewave.com/threadspotter/2010.4/manual/ch03s02.html) 

4.401.bzip2 SPEC CPU2006 Benchmark Description File [https://www.spec.org/cpu2006/Docs/401.bzip2.html](https://www.spec.org/cpu2006/Docs/401.bzip2.html) 

5.429.mcf SPEC CPU2006 Benchmark Description File [https://www.spec.org/cpu2006/Docs/429.mcf.html](https://www.spec.org/cpu2006/Docs/429.mcf.html) 

6.456.hmmer SPEC CPU2006 Benchmark Description File [https://www.spec.org/cpu2006/Docs/456.hmmer.html](https://www.spec.org/cpu2006/Docs/456.hmmer.html) 

7.458.sjeng SPEC CPU2006 Benchmark Description File [https://www.spec.org/cpu2006/Docs/458.sjeng.html](https://www.spec.org/cpu2006/Docs/458.sjeng.html) 

8.470.lbm SPEC CPU2006 Benchmark Description File [https://www.spec.org/cpu2006/Docs/470.lbm.html](https://www.spec.org/cpu2006/Docs/470.lbm.html) 

9.Slides about Cache performace from Electrical and Computer Engineering Department of University of New Mexico [http://ece-research.unm.edu/jimp/611/slides/chap5_2.html](http://ece-research.unm.edu/jimp/611/slides/chap5_2.html) 

10.Slides about Cache Organization from University of Washington [https://courses.cs.washington.edu/courses/cse378/09au/lectures/cse378au09-20.pdf](https://courses.cs.washington.edu/courses/cse378/09au/lectures/cse378au09-20.pdf) 

11.Υλικό Μαθήματος της Αρχιτεκτονικής Υπολογιστών [https://elearning.auth.gr/course/view.php?id=12158](https://elearning.auth.gr/course/view.php?id=12158)  
