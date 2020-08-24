
## Install

```
# install.packages("devtools")
devtools::install_github("mattocci27/NST")
```


## Example

- Use the original sample size for each group for resampling.

```
data(tda)
comm=tda$comm
group=tda$group
tnst=tNST(comm=comm, group=group, rand=20,
          output.rand=TRUE, nworker=1)
# rand is usually set as 1000, here set rand=20 to save test time.

nst.bt=nst.boot(nst.result=tnst, group=NULL, rand=99,
                trace=TRUE, two.tail=FALSE, out.detail=FALSE,
                between.group=FALSE, nworker=1)
```


- Apply the minimum sample size (`n.min`) for resampling for each group.

```
nst.bt2=nst.boot(nst.result=tnst, group=NULL, rand=99,
                trace=TRUE, two.tail=FALSE, out.detail=FALSE,
                between.group=FALSE, 
                n.min = 12,
                nworker=1)
```
