## Usage

```yaml
name: Test
on: push
jobs:
  test:
    runs-on: ubuntu-latest

    steps:
      - name: Test
        run: npm run test

      - name: Notify
        if: always()
        uses: aslafy-z/freemobile-sms-action@master
        with:
          freemobile_id: ${{ secrets.freemobile_id }}
          freemobile_token: ${{ secrets.freemobile_token }}
          message: |
            ${{ github.repository }}@${{ github.ref }} result: ${{ job.status }}.
```
