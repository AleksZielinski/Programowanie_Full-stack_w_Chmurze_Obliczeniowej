1\) Wersja jednorazowa (zakończy się "Completed") -> Plik loop-pod.yaml



\*\*Tworzenie i weryfikacja:\*\*

&nbsp;   kubectl apply -f loop-pod.yaml

&nbsp;   kubectl get pods

&nbsp;   kubectl logs loop



\*\*Oczekiwany rezultat:\*\*

\- Status Poda: "Completed"

\- Logi:

&nbsp;   1 - A piece of cake !

&nbsp;   2 - A piece of cake !

&nbsp;   3 - A piece of cake !

&nbsp;   4 - A piece of cake !

&nbsp;   5 - A piece of cake !

---



2\) Wersja utrzymująca stan "Running" -> Plik loop-pod-running.yaml



\*\*Uruchomienie (najpierw usuwamy poprzedniego Poda):\*\*



&nbsp;   kubectl delete pod loop

&nbsp;   kubectl apply -f loop-pod-running.yaml

&nbsp;   kubectl get pods

&nbsp;   kubectl describe pod loop

&nbsp;   kubectl logs loop



\*\*Oczekiwany rezultat:\*\*

\- Status Poda: "Running"

\- Logi zawierają te same 5 linii, a kontener dalej działa dzięki "sleep infinity".

---



\## Sprzątanie



&nbsp;   kubectl delete pod loop --ignore-not-found



---





