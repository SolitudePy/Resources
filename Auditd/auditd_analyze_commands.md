# Most noisy events by keys
aureport -k | awk '{print $4}' | sort | uniq -c | sort -n