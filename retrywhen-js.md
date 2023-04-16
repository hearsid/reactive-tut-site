Preface:
Many times in Angular we get to deal with external components that don't have a proper initialization hook defined. I faced similar issue with primeng table where there was no specific lifecycle hook to indicate if the table has been initiated. 
To solve this issue, rxjs can be used to create an observable that keep checking at certain interval if the element is defined and once the element is defined call the desired method.

const tableDefined$ = new Observable((observer) => {

      if (!this.table || this.table._columns === undefined) {
        observer.error('Table not defined.');
      } else if (this.table._columns.length > 0) {
        observer.next(this.table._columns);
        observer.complete();
      }
    });

    tableDefined$.pipe(retryWhen(concatMap((err, index) => (index < 14 ? timer(300) : throwError(err))))).subscribe(() => {
      this.setCustomColWidth();
    });

Give detailed example of same with stackblitz link:
https://stackblitz.com/edit/angular-hfizjn?file=src/app/app.component.html

