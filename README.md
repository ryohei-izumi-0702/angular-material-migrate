# angular-material-migrate


```
@use '@angular/material' as mat;

$primary: mat.m2-define-palette(mat.$deep-purple-palette);
$accent: mat.m2-define-palette(mat.$amber-palette);
$warn: mat.m2-define-palette(mat.$red-palette);

$theme: mat.m2-define-light-theme((
  color: (
    primary: $primary,
    accent: $accent,
    warn: $warn,
  )
));

@include mat.all-component-themes($theme);

/* M2風の mat-table 調整 */
::ng-deep .mat-mdc-table {
  border-collapse: collapse;
}

::ng-deep .mat-mdc-header-cell {
  background-color: mat.get-color-from-palette($primary, 50); // M2風の薄い色
  font-weight: 500;
  padding: 0 24px;
  height: 56px;
}

::ng-deep .mat-mdc-cell {
  border-bottom: 1px solid rgba(0, 0, 0, 0.12);
  padding: 0 24px;
  height: 48px;
}


/* チェックボックスサイズをM2相当に */
::ng-deep .mat-mdc-checkbox .mat-mdc-checkbox-background {
  width: 18px;
  height: 18px;
}

/* 枠線を細く */
::ng-deep .mat-mdc-checkbox .mat-mdc-checkbox-background {
  border-width: 2px;
}

/* ラベルの位置とフォントサイズをM2風に */
::ng-deep .mat-mdc-checkbox-label {
  font-size: 14px;
  line-height: 18px;
  padding-left: 8px; /* M2風の余白 */
}

/* チェックマークカラーをM2テーマ色に */
@use '@angular/material' as mat;
$primary: mat.m2-define-palette(mat.$deep-purple-palette);

::ng-deep .mat-mdc-checkbox.mat-accent .mat-mdc-checkbox-background {
  background-color: mat.m2-get-color-from-palette($primary);
  border-color: mat.m2-get-color-from-palette($primary);
}
```

