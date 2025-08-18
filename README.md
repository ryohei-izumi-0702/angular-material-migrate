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
@use '@angular/material' as mat;

$primary: mat.m2-define-palette(mat.$deep-purple-palette);
$checkmark-color: mat.m2-get-color-from-palette($primary, default-contrast);

$checkmark-color: mat.m2-get-color-from-palette($primary, default-contrast);

::ng-deep .mat-mdc-checkbox .mat-mdc-checkbox-checkmark-path {
  stroke: $checkmark-color; /* チェックマーク線の色 */
}

::ng-deep .mat-mdc-checkbox .mat-mdc-checkbox-checkmark-path {
  stroke: $checkmark-color; /* チェックマーク線の色 */
}


::ng-deep .mat-mdc-slider {
  height: 2px; // M2相当の細いトラックにする
  margin: 10px 0;
}

::ng-deep .mat-mdc-slider .mdc-slider__track {
  height: 2px;
  background-color: mat.m2-get-color-from-palette($primary, 500);
}

::ng-deep .mat-mdc-slider .mdc-slider__thumb {
  width: 12px;
  height: 12px;
  background-color: mat.m2-get-color-from-palette($primary, 500);
  border: none;
}

::ng-deep .mat-mdc-slider .mdc-slider__track--inactive {
  background-color: rgba(0, 0, 0, 0.26); // M2っぽい非アクティブカラー
}

::ng-deep .mat-mdc-slider .mdc-slider__thumb:focus {
  box-shadow: none; // M3特有の青いリングを無効に
}

## or

::ng-deep .mat-mdc-slider {
  --mdc-slider-handle-color: #673ab7;
  --mdc-slider-track-active-color: #673ab7;
  --mdc-slider-track-inactive-color: rgba(0, 0, 0, 0.26);
  --mdc-slider-focus-handle-color: transparent;
  --mdc-slider-hover-handle-color: #673ab7;
}

/* mat-slider の目盛り（tick marks）を非表示にしてM2風に */
::ng-deep .mat-mdc-slider .mdc-slider__tick-marks {
  display: none !important;
}

@use '@angular/material' as mat;
$primary: mat.m2-define-palette(mat.$deep-purple-palette);

/* M2風の mat-slider バー補正 */
::ng-deep .mat-mdc-slider .mdc-slider__track {
  height: 2px !important;         // M2の細さ
  border-radius: 0 !important;    // M2では角丸なし
}

::ng-deep .mat-mdc-slider .mdc-slider__track--active,
::ng-deep .mat-mdc-slider .mdc-slider__track--inactive {
  border-radius: 0 !important;    // セグメントの角丸も除去
}

::ng-deep .mat-mdc-slider .mdc-slider__track--active {
  background-color: mat.m2-get-color-from-palette($primary, 500) !important;
}

::ng-deep .mat-mdc-slider .mdc-slider__track--inactive {
  background-color: rgba(0, 0, 0, 0.26) !important;
}
```

