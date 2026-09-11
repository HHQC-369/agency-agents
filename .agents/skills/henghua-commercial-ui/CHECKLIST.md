# Henghua Commercial UI Checklist

Use this during implementation and review.

## Visual system
- [ ] Shared color tokens
- [ ] Shared typography scale
- [ ] Shared spacing scale
- [ ] Shared control heights
- [ ] Consistent radius/border/elevation
- [ ] One icon language
- [ ] Semantic status colors separated from brand color
- [ ] Hover/focus/pressed/disabled/read-only states defined

## WPF / WinUI
- [ ] No conflicting implicit styles
- [ ] Resource lookup order verified
- [ ] Commands reflect real availability
- [ ] Dialog ownership/focus return correct
- [ ] Virtualization retained
- [ ] No avoidable UI-thread blocking
- [ ] Theme behavior verified

## ERP / MES
- [ ] Filters visible and resettable
- [ ] Batch actions explicit
- [ ] Business statuses unambiguous
- [ ] Production states complete
- [ ] Permission boundaries visible
- [ ] Totals and key metrics stable

## Printing
- [ ] Real printer identity
- [ ] Media/paper/orientation clear
- [ ] Mono/color clear
- [ ] Copies/page range/scaling clear
- [ ] Queue/progress/cancel/failure handled
- [ ] Submitted != completed

## Finance
- [ ] Currency/precision consistent
- [ ] Negative values clear
- [ ] Partial payments handled
- [ ] Refund/reversal distinct
- [ ] Posted/closed states read-only
- [ ] Audit-sensitive actions show operator/time/reason

## DataGrid
- [ ] Column order matches workflow
- [ ] Numeric alignment correct
- [ ] Sorting/filter state visible
- [ ] Keyboard navigation works
- [ ] Selection/edit modes clear
- [ ] Large datasets virtualized
- [ ] Empty/loading/error states exist
- [ ] Long Chinese text does not break layout

## Windows / DPI
- [ ] 100%
- [ ] 125%
- [ ] 150%
- [ ] 175%
- [ ] 200%
- [ ] Multi-monitor DPI transition
- [ ] Minimum window size
- [ ] No clipped Chinese labels
- [ ] Popup/dialog placement stays onscreen
- [ ] Windows 10 fallback behavior

## Release
- [ ] P0 = 0
- [ ] P1 = 0
- [ ] P2 accepted or fixed
- [ ] Representative runtime screenshots reviewed
- [ ] No regression outside modified scope
- [ ] Known limitations documented
