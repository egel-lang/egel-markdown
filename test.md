.using System;;

.egel
    def fac = [0 -> 1 |N -> N * fac (N - 1)];;

Amazingly, the factorial of 5 is {{fac 5}}.

{{0}}{{3}}{{4.15}}

.import "prelude.eg";;
.using List;;
.data branch, leaf;;
.def exclamation = [L -> L + "!"];;
.val global = ref 3.14;;

.hook (map exclamation);;
.hook (map exclamation);;